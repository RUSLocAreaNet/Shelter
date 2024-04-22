<script setup>
import { ref } from 'vue';

var sports = ref();
async function fetchsports ()
{
    var stuff;
    await fetch("http://localhost:3000/sports").then(response => response.json()).then(
        data => {stuff = data; console.log(data);})
    sports = stuff;
}

fetchsports()
</script>

<template>
     <div>
        <span>
            <div>
            Icon shall be here
            </div>
            <div>
                <label for="sports"> Choose sport</label>
                <select id = "sports" class="button" v-for="sport in sports">
                    <option><div>SPORT</div></option>
                    <option><div>SPIRT</div></option>
                    <!-- <span>
                        <div>
                            {{ sport.sporticon }}
                        </div>
                        <div>
                            {{ sports.sport }}
                        </div>
                    </span>-->
                </select>
            </div>
        </span>
            
        <div>
            <li v-for="activity in activities">
                <div>{{ activity.date }}</div><div> {{activity.amount}} </div>
            </li>
        </div>
    </div>
</template>





// TODAY AFTER COMING HOME I CREATE SQL DATABASE AND NODE SERVER AS WELL AS TOMORROW I MAKE FETCHES WORK