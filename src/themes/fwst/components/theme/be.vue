<template>
<div class="container-fluid">
  <div class="container" >
    <div class="row">
      <div class="container col-6" >
        <figure class="fir-image-figure" v-for="(name) in names" :key="name.title">

          <a class="fir-imageover" rel="noopener" target="_blank" href="">
            <img class="fir-author-image fir-clickcircle" :src="'/assets/images/' + name.image" alt="">
            <div class="fir-imageover-color"></div>
          </a>

          <figcaption class="text-left">
          <div class="fig-author-figure-title">{{name.date}} | {{name.name}}</div>
          <div class="title">{{name.title}}</div>
          <div class="subtitle">{{name.subtitle}}</div>
          </figcaption>
        </figure>
      </div>
        <div class="board-container col-4">
          <div class="board">
          <h2 class="eventhead">UPCOMING EVENTS</h2>

          </div>
        </div>


    </div>
    <div class="latest-news__footer col-3" ><a href="" class="btn-link p-0"> View All Blogs </a></div>
  </div>
</div>


</template>

<script>

export default {

  props: ['words', 'words2'],
  computed: {

    names() {
      return this.words2.blog.map((item) => {

        return item;
      })
    },
    names1() {
      return this.words.event.map((item) => {

        return item;
      })
    }
  },

  components: {

  }
    }
</script>


<style scoped lang="css">

:root {
  --fir-font-article: "adobe-garamond-pro", "Times New Roman", Times;
  --fir-font-header: "foco", Helvetica;
  --fir-blue-twitter-alpha: rgba(85,172,238, 0.6);
  --fir-color-grey: rgba(0,0,0, 0.40);
}


.fir-clickcircle {
  height: 125px;
  width: 125px;
  border-radius: 100px;
  cursor: pointer;
}

.fir-image-figure {
  margin: 0;
  display: flex;
  margin-bottom: 40px;
  position: relative;
  text-decoration: none;
}

.fir-image-figure .caption, .fir-image-figure figcaption {
  padding-left: 15px;
}

html.wf-active .fir-image-figure .fig-author-figure-title {
  font-family: var(--fir-font-header);
  font-size: 16px;
}

.fir-image-figure .fig-author-figure-title {
  color: var(--fir-color-grey);
  font-family: "HelveticaNeue-Light", "Helvetica Neue Light", "Helvetica Neue", Helvetica, Arial, "Lucida Grande", sans-serif;
  font-weight: 400;
  font-size: 14px;
  margin-top: 2px;
}

.fir-imageover {
  position: relative;
  display: flex;
}

.fir-imageover-color {
  height: 100px;
  width: 100px;
  position: absolute;
  background: var(--fir-blue-twitter-alpha);
  background-image: none;
  border-radius: 100px;
  cursor: pointer;
  transition: background .3s ease-in-out;
  animation: fadeInFadeOut 2s infinite;
  top: 0;
  left: 0;
}

.fir-imageover-image {
  position: absolute;
  top: 0;
  left: 0;
  animation: fadeInFadeOut 2s infinite;
}

@keyframes fadeInFadeOut {
  0%   { opacity:1; }
  50%  { opacity:0; }
  100% { opacity:1; }
}

.title{
  font-family: var(--fir-font-header);
  font-size: 20px;
}

.subtitle{
  font-family: var(--fir-font-header);
  font-size: 16px;

}
.board-container{
  padding:30px;
  box-sizing:border-box;

  }
.board{
  background-color:#3c3c3c;
  height:100%;
  padding:30px;
  text-align: left;

  }
.eventhead{
  color:#fff;
  font-size: 20px;
  border-bottom: 1px solid #fff;
  opacity: 60%;
}
.btn-link {
    font-weight: 400;
    color: black;
    text-decoration: none;
    border-bottom: 1px solid black;
}
</style>
