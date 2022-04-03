<template>
<div class="ingredients">
<h1>Ingredients</h1>
  <section class="ingredient-gallery">
    <div class="ingredient" v-for="item in items" :key="item.id">
      <h1>{{item.title}}</h1>
      <h5>{{item.description}}</h5>
    </div>
  </section>

</div>

</template>
<style scoped>
.ingredient h1 {
display: flex;
justify-content: flex-start;
padding-left: 20px;
}
.ingredient h5 {
padding-top: 5px;
padding-left: 20px;
}

*,
*:before,
*:after {
  box-sizing: inherit;
}
.ingredient-gallery {
	column-gap: 1.5em;
}
.ingredient {
  margin: 0 0 1.5em;
  display: inline-block;
  width: 100%;
border: 1px solid black;
background-color: #fff4eb;
}
/* Masonry on large screens */
@media only screen and (min-width: 1024px) {
  .ingredient-gallery {
    column-count: 1;
  }
}
/* Masonry on medium-sized screens */
@media only screen and (max-width: 1023px) and (min-width: 768px) {
  .ingredient-gallery {
    column-count: 3;
  }
}
/* Masonry on small screens */
@media only screen and (max-width: 767px) and (min-width: 540px) {
  .ingredient-gallery {
    column-count: 2;
  }
}
</style>

<script>
// @ is an alias to /src
import axios from 'axios';
export default {
  name: 'Recipes',
  data() {
    return {
      items: [],
    };
  },
  created() {
    this.getItems();
  },
  methods: {
    async getItems() {
      try {
        let response = await axios.get("/api/items");
	this.items = response.data;
	return true;
      } catch (error) {
       // console.log(error);
      }
    },
  },
};
</script>
