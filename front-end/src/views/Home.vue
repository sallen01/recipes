
   
<template>
<div class="home">
<h1>Recipes</h1>
  <section class="image-gallery">
    <div class="image" v-for="item in items" :key="item.id">
      <h1>{{item.title}}</h1>
	<div class=image-container>
	<router-link to="/recipes">
	<img :src="item.path" />
	</router-link>
	</div>
    </div>
  </section>

</div>

</template>

<style scoped>
.image h1 {
display: flex;
justify-content: center;
}
.image h5 {
display: flex;
justify-content: center;
padding-top: 5px;
}

*,
*:before,
*:after {
  box-sizing: inherit;
}
.image-gallery {
  column-gap: 1.5em;
}
.image {
  margin: 0 0 1.5em;
  display: inline-block;
  width: 100%;
border: 1px solid black;
height: 200px;
background-color: #fff4eb;
padding-bottom: 20px;
}
.image img {
width: 100px;
display: flex;
justify-content: center;
//width: 50%;
}
.image-container {
display: flex;
justify-content: center;
}
/* Masonry on large screens */
@media only screen and (min-width: 1024px) {
  .image-gallery {
    column-count: 4;
  }
}
/* Masonry on medium-sized screens */
@media only screen and (max-width: 1023px) and (min-width: 768px) {
  .image-gallery {
    column-count: 3;
  }
}
/* Masonry on small screens */
@media only screen and (max-width: 767px) and (min-width: 540px) {
  .image-gallery {
    column-count: 2;
  }
}
</style>

<script>
// @ is an alias to /src
import axios from 'axios';
export default {
  name: 'Home',
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
