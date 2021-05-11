<template>
<div>

  <infinite-slide-bar duration="90s" direction="normal" delay="2s" :barStyle="{ background: '#fff', padding: '0 0' , margin: '0px 50px'}">


    <div class="items">

      <div v-for="(brand,index) in brandArray" :key="index">
        <!-- <div class="">
          <div class="font-weight-bold" style="text-transform: uppercase; ">{{brand.name}}</div>
        </div> -->

        <div class="mx-4" style="width:170px">
          <img :src="'/assets/componentAssets/fwBrandSliderImg/'+ brand.pic">
        </div>
      </div>

    </div>
  </infinite-slide-bar>

</div>

</template>

<style scoped>
.items { display: flex; justify-content: space-around; }
</style>

<script>
import InfiniteSlideBar from 'vue-infinite-slide-bar'


export default {
  props: ['words'],
  data: function () {
    return {
      options: {
        barStyle: '',
        duration: '24s',
        direction: 'normal',
        delay: '0s',
        paused: false
      }
    }
  },
  computed: {
    brandArray() {
      return this.words.brands.map((item) => {
        return item;
      })
    }
  },

  mounted() {

  },
  methods: {

  },
  components: {
    InfiniteSlideBar
  },
  filters: {

  }
}
</script>
