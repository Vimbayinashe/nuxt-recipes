<template>
  <nuxt-link :to="'/recipes/' + id">
    <article class="recipe">
      <div class="thumbnail" :style="{backgroundImage: `url(${thumbnail})`}"></div>
      <h1>{{ title }}</h1>
      <p>{{ previewText }} </p>
    </article>
  </nuxt-link>
</template>

<script>
export default {
  props: {
    thumbnail: String,
    title: String,
    previewText: String,
    id: String
  }
  
  // props: []
}
</script>

<style scoped> 

a {
  color: black;
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
  font-size: 105%;
}

/* a:hover {
  transition: font-size 1s;
} */

.recipe {
  box-sizing: border-box;
  width: 280px;
  padding: 8px;
  border: 1px solid grey;
  box-shadow: 0 2px 2px #aaa;
  margin: 1em;
}

.thumbnail {
  background-position: center;
  background-size: cover;
  background-image: url('https://www.bbcgoodfood.com/sites/default/files/recipe-collections/collection-image/2013/05/chorizo-mozarella-gnocchi-bake-cropped.jpg');
  height: 200px;
  width: 100%;
}
</style>