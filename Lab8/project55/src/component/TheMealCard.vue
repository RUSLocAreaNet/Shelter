<script setup>
import {ref, onMounted, resolveComponent} from 'vue';
const recipe = ref({});

async function getRecipe()
  {

    let idiocy;
  const response = await fetch("https://www.themealdb.com/api/json/v1/1/random.php")
  const data = await response.json();
  console.log("thehell");
  idiocy = await data.meals[0];
  console.log(idiocy);
  recipe.value = await idiocy;
  console.log(recipe.value);
  listThrough20IngredientsAndValues();
  }

  function listThrough20IngredientsAndValues()
  {
    let n = 1;
    let markup = "<tr><td><b>Ingredient</b></td><td><b>Amount</b></td></tr>";
    let Id = `strIngredient1`;
    let IM = `strMeasure1`;
    console.log("started");
    while (recipe.value[Id] != "" && n<=20)
    {
      Id = `strIngredient${n}`;
      IM = `strMeasure${n}`;
      if(recipe.value[Id] == "")
      {
        break;
      }
      console.log(recipe.value[Id])
      console.log(recipe.value[IM])
      markup += `<tr><td>${recipe.value[Id]}</td><td>${recipe.value[IM]}</td></tr>`;
      n++;
    }
    console.log("ended")
    console.log(markup)
    document.getElementById("IL").innerHTML = markup;
    return markup;
  }
  //<img v-bind:src="recipe.value.strMealThumb">

  onMounted(() => {getRecipe();});
</script>

<template>
  <div class="text-center">
    <button class="rounded bg-primary my-3 py-2 px-5" @click="getRecipe()"> New recipe</button>
  </div>
  <div class="row w-75">
    <table class="card card-body table table-striped col-sm-2 offset-sm-4">
      <tbody class="text-center">
        <tr class="text-center">
          <td class="text-center">
            <h5 class="text-center"> {{ recipe.strMeal }}</h5>
          </td>
        </tr>
      <tr>
        <td class="text-center">
          <img class="img-fluid" v-bind:src="recipe.strMealThumb">
        </td>
      </tr>
      <tr>
        <td>
          <table class = "table table-striped" id="IL">
          </table>
        </td>
      </tr>
      <tr>
        <td>
          {{ recipe.strInstructions }}
        </td>
      </tr>
      </tbody>
    </table>
  </div>
</template>

<style scoped>
</style>