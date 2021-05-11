<template>

<div class="container-fluid">

  <input type="radio" name="position"  />
  <input type="radio" name="position" />
  <input type="radio" name="position" checked />
  <input type="radio" name="position" />
  <input type="radio" name="position" />
  <main id="carousel" class="carousel slide" data-interval="3000">
    <div class="item">
		<div class="carousel-inner">
        <div v-for="(name, index) in names" :key="name.title"  :id="index" class="carousel-item " :class="{ 'active': index === 0 }">
          <img :src="'/assets/images/' + name.image" class="d-block w-100" alt="">
          <div class="carousel-caption d-none d-md-block">
            <h5 class="slide-title">{{ name.title }}</h5>
            <p class="slide-sub-title">{{ name.subtitle }}</p>
          </div>
        </div>
      </div>
	</div>
    <div class="item">

	</div>
    <div class="item">

	</div>
    <div class="item">

	</div>
    <div class="item">

	</div>
  </main>

</div>

</template>

<script>

export default {

    props: ['bgColor', 'words'],
  computed: {

    names() {
      return this.words.promos.map((item) => {

        return item;
      })
    }
  },

  components: {

  }
    }


</script>

<style scoped lang="css">
/* Slider */
.carousel-item {
  height: 25vh;
  padding: 0 40px;
  background-repeat: no-repeat;
  background-position: center center;
  background-size: cover;
}
.multi-item-carousel{
  .carousel-inner{
    > .item{
      transition: 500ms ease-in-out left;
    }
    .active{
      &.left{
        left:-33%;
      }
      &.right{
        left:33%;
      }
    }
    .next{
      left: 33%;
    }
    .prev{
      left: -33%;
    }
    @media all and (transform-3d), (-webkit-transform-3d) {
      > .item{
        transition: 500ms ease-in-out left;
        transition: 500ms ease-in-out all;
        backface-visibility: visible;
        transform: none!important;
      }
    }
  }
}


main#carousel {
  grid-row: 1 / 2;
  grid-column: 1 / 8;
  width: 100vw;
  height: 200px;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  transform-style: preserve-3d;
  perspective: 600px;
  --items: 5;
  --middle: 3;
  --position: 1;
  pointer-events: none;
}

div.item {
  position: absolute;
  width: 600px;
  height: 200px;
  background-color: coral;
  --r: calc(var(--position) - var(--offset));
  --abs: max(calc(var(--r) * -1), var(--r));
  transition: all 0.25s linear;
  transform: rotateY(calc(-10deg * var(--r)))
    translateX(calc(-300px * var(--r)));
  z-index: calc((var(--position) - var(--abs)));
}

div.item:nth-of-type(1) {
  --offset: 1;
  background-color: #ccc;
}
div.item:nth-of-type(2) {
  --offset: 2;
  background-color: #aaa;
}
div.item:nth-of-type(3) {
  --offset: 3;
  background-color: #ccc;
}
div.item:nth-of-type(4) {
  --offset: 4;
  background-color: #aaa;
}
div.item:nth-of-type(5) {
  --offset: 5;
  background-color: #ccc;
}

input:nth-of-type(1) {
  grid-column: 2 / 3;
  grid-row: 2 / 3;
}
input:nth-of-type(1):checked ~ main#carousel {
  --position: 1;
}

input:nth-of-type(2) {
  grid-column: 3 / 4;
  grid-row: 2 / 3;
}
input:nth-of-type(2):checked ~ main#carousel {
  --position: 2;
}

input:nth-of-type(3) {
  grid-column: 4 /5;
  grid-row: 2 / 3;
}
input:nth-of-type(3):checked ~ main#carousel {
  --position: 3;
}

input:nth-of-type(4) {
  grid-column: 5 / 6;
  grid-row: 2 / 3;
}
input:nth-of-type(4):checked ~ main#carousel {
  --position: 4;
}

input:nth-of-type(5) {
  grid-column: 6 / 7;
  grid-row: 2 / 3;
}
input:nth-of-type(5):checked ~ main#carousel {
  --position: 5;
}


</style>
