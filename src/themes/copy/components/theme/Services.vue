<template>
    <div class="container-fluid">
        <div class="container">
            <div class="row my-2">
                <div v-for="(name) in names" :key="name.title" class="col-12 col-lg-4 p-2">
                    <div class="card">
                        <img :src=" '/assets/images/' + name.image" alt="" class="card-img-top">
                        <div class="card-body">
                            <h5 class="card-title">{{ name.title }}</h5>
                            <p class="card-text">{{ name.text }}</p>
                            <a :href="name.link" class="btn btn-outline-success btn-sm">{{ name.button_text }}</a>

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

</style>
