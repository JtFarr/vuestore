<template>
  <div class="container-fluid">
      <div class="container">
          <div class="row my-2">
              <div v-for="(name) in names" :key="name.title" class="col-12 col-lg-4 p-2">
                  <div class="card border-0 bg-transparent pt-3 pb-1 px-2">
                      <!-- <img :src=" '/assets/images/' + name.image" alt="" class="card-img-top"> -->
                      <div class="card-body back" :style='{ backgroundImage: "url("+ imgUrl + name.image + ")", }'>
                        <div class="head">
                          <div class="text">
                            {{ name.title }}
                          </div>
                        </div>
                          <!-- <h5 class="card-title">{{ name.title }}</h5> -->
                          <!-- <p class="card-text">{{ name.text }}</p> -->
                          <!-- <a :href="name.link" class="btn btn-outline-success btn-sm">{{ name.button_text }}</a> -->

                      </div>
                  </div>
              </div>
          </div>
      </div>
  </div>
</template>

<script>


export default {
  props: ['bgColor', 'words'],
  data: function () {
    return {
      imgUrl: "/assets/componentAssets/fwServicesImg/"
    }
  },
  computed: {

    names() {
      return this.words.services.map((item) => {
        return item;
      })
    }
  },
  components: {

  }
}
</script>

<style scoped lang="css">
.back {
  min-height:300px;
  /* opacity: 80%; */
  background-position: center; /* Center the image */
  background-repeat: no-repeat; /* Do not repeat the image */
  background-size: cover; /* Resize the background image to cover the entire container */
  box-shadow: 2px 2px 10px #323232;
}
.back:hover {
  box-shadow: 0px 0px 5px #323232;
}
.head {
  position:absolute;
  top:0;
  left:0;
  width: 80%;
  padding: 10px;
  box-shadow: 2px 2px 10px #838383;
  background-color: rgb(0,0,0, .9);
  text-align:left;
}

.head .text {
  color: #D4AF37;
  font-size:20px;
  font-weight: 900;
  text-transform: uppercase;
}

</style>
