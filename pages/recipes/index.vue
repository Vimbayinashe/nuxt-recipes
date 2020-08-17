<template>
  <section class="recipes">
    
    <Recipe
      v-for="recipe in recipes"
      :key="recipe.id"
      :thumbnail="recipe.thumbnail"
      :title="recipe.title"
      :previewText="recipe.previewText"
      :id="recipe.id" />

    <!-- <Recipe 
      thumbnail="https://www.bbcgoodfood.com/sites/default/files/recipe-collections/collection-image/2013/05/chorizo-mozarella-gnocchi-bake-cropped.jpg"
      title="Vegetables!!"
      previewText="Yummy..." 
      id="3" /> -->

  </section>
</template>

<script>
import Recipe from '@/components/Recipe';

export default {
  components: {
    Recipe
  },

  // data() {   //replaced by asyncData
  //   return
  // }

  asyncData() {
    // executed on the server to fetch all the data which needs to be rendered in advance before the page loads, 
    // comparable with normal data() method in Vue. In vue data is only fetched when a user clicks on the client side

    // below data can be replaced with an axios call //return axios.get()
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipes: [
            {
              id: "1",
              title: "New Recipe",
              previewText: "Delicious Recipe",
              thumbnail: "https://ichef.bbci.co.uk/news/695/cpsprodpb/BE2D/production/_112058684_gettyimages-1208790371.jpg"
            },
            {
              id: "2",
              title: "Carrot Cake",
              previewText: "The Best Cake ever!!!",
              thumbnail: "https://www.bbcgoodfood.com/sites/default/files/styles/recipe/public/recipe/recipe-image/2018/07/carrot-cake.jpg?itok=kNdPtNPm"
            },
            {
              id: "3",
              title: "Gnocchi Bake",
              previewText: "Yummy...",
              thumbnail: "https://www.bbcgoodfood.com/sites/default/files/recipe-collections/collection-image/2013/05/chorizo-mozarella-gnocchi-bake-cropped.jpg"
            },
          ]
        })
      }, 1500)
    })

  }

}
</script>

<style scoped>
.recipes {
  display: flex;
  flex-flow: row wrap;  /** combo of wrap flex-wrap & flex-direction */
  justify-items: center;
  align-items: center;
}


</style>

