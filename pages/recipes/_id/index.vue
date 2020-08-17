<template>
  <section class="single-recipe">
    <h1>{{ recipe.title }}</h1>
    <div>
      <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title">
    </div>
    <p> {{ $route.params.id }}. {{ recipe.descriptionText}}</p>

  </section>
</template>

<script>
export default {

  // $route.params is not available before the page has loaded, however
  // context can parse the params from url link (line 41) 
  asyncData(context) {

    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipe: [
            {
              id: "1",
              title: "New Recipe",
              previewText: "Delicious Recipe",
              descriptionText: "This is really delicious!",
              thumbnail: "https://ichef.bbci.co.uk/news/695/cpsprodpb/BE2D/production/_112058684_gettyimages-1208790371.jpg"
            },
            {
              id: "2",
              title: "Carrot Cake",
              previewText: "The Best Cake ever!!!",
              descriptionText: "This is really delicious!",
              thumbnail: "https://www.bbcgoodfood.com/sites/default/files/styles/recipe/public/recipe/recipe-image/2018/07/carrot-cake.jpg?itok=kNdPtNPm"
            },
            {
              id: "3",
              title: "Gnocchi Bake",
              previewText: "Yummy...",
              descriptionText: "This is really delicious!",
              thumbnail: "https://www.bbcgoodfood.com/sites/default/files/recipe-collections/collection-image/2013/05/chorizo-mozarella-gnocchi-bake-cropped.jpg"
            },
          ].find(recipe => recipe.id === context.params.id)
        })
      }, 1500)
    })

  }

}
</script>

<style scoped>
.single-recipe {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 2em;
}

.recipe-image {
  width: 100%;
}
</style>