<template>

<div id="carouselExampleCaptions" class="carousel slide" data-ride="carousel">
  <ol class="carousel-indicators">
    <li v-for="(name, index) in names" :key="name.title" data-target="#carouselExampleCaptions" :data-slide-to="index" :class="{ 'active': index === 0 }"></li>
  </ol>

      <div class="carousel-inner">
        <div v-for="(name, index) in names" :key="name.title"  :id="index" class="carousel-item " :class="{ 'active': index === 0 }">
          <img :src="'/assets/componentAssets/fwSliderImg/' + name.image" class="d-block w-100" alt="">
          <div class="carousel-caption d-none d-md-block">
            <h5 class="slide-title">{{ name.title }}</h5>
            <p class="slide-sub-title">{{ name.subtitle }}</p>
          </div>
        </div>
      </div>

  <a class="carousel-control-prev" href="#carouselExampleCaptions" role="button" data-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="sr-only">Previous</span>
  </a>
  <a class="carousel-control-next" href="#carouselExampleCaptions" role="button" data-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="sr-only">Next</span>
  </a>

</div>

</template>

<script>

export default {

  props: ['bgColor', 'words'],
  computed: {

    names() {
      var _this = this;
      return _this.words.slide.map((item) => {

        return item;
      })
    }
  },

  components: {

  }
    }
</script>

<style scoped lang="css">

</style>
