<template>
  <header>
    <nav>
      <ul>
        <li><nuxt-link to="/">Start</nuxt-link></li>
        <li><nuxt-link to="/recipes">Recipes</nuxt-link></li>
        <li><nuxt-link to="/about">About</nuxt-link></li>
      </ul>
    </nav>
  </header>
</template>

<style scoped>
  header {
    background-color: #521751;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 3em;
    margin: 0;
    width: 100%;
  }

  ul {
    display: flex;
    justify-content: center;
    list-style: none;
    margin: 0;
    padding: 0;
    align-items: center;
  }

  li {
    margin: 0 10px;
  }

  a {
    color: white;
    font-size: 1.3em;
    text-decoration: none;
  }
</style>