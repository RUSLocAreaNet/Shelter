<script setup>
import { onMounted, ref } from 'vue';
import Overview from '../views/OverViewView.vue'

var activities = ref();
var sports = ref();
async function getUserActivities(sport)
{
    //fetch activities for chosen sport and place them inside of the variable, format them to be a json array
}
async function fetchSports()
{
    //fetch sports and place them inside of a variable OR session storage
}


</script>

<template>
   <Overview />
</template>