<template>
  <div class="container-fluid p-4">
    <div class="container">
      <div class="row">
        <div class="col-12">

          <div class="card-deck">

            <div v-for="(name) in names" :key="name.title" class="card img-fluid " >
            <img class="" :src="'./assets/images/' + name.image" alt="Card image cap">
              <div class="header " style="">
                <p class="text" style="text-transform: uppercase;">{{ name.title }}</p>
              </div>
              <div class="info">
                <h1>{{ name.title }}</h1>
                <div>{{ name.subtitle }}</div>

                <div class="">
                  <span v-for="(cats, index) in name.cat" :key="cats.title" class="text2" style="inline">
                    {{cats.title}}<span v-if="(index + 1) < name.cat.length">, </span>
                  </span>
                </div>

                <button>Read More</button>

              </div>
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
      return this.words.categories.map((item) => {
        return item;
      })
    }
  },
  components: {

  }
}
</script>

<style scoped>


/* .card { */
  /* width: 280px;
  height: 360px; */
  /* border-radius: 15px;
  padding: 1.5rem;
  background: white;
  position: relative;
  display: flex;
  align-items: flex-end;
  transition: 0.4s ease-out;
  box-shadow: 0px 7px 10px rgba(0, 0, 0, 0.5);
} */
/* .header {
  z-index: 1;
  width: 100%;
  color: #fff;
  border: none;
  font-weight: 700;

} */
/* .header .text {
  position: absolute;
  top: 5%;
  left: 5%;
  transition: opacity .5s;
} */
/* .card:hover .header .text {
  opacity: .0; */
  /* right: 60%;
  font-size: 150%; */
  /* transform: translateX(250%);
  -ms-transform: translateX(250%); */
  /* z-index: -1 */
/* } */
/* .card:hover {
  transform: translateY(20px);
} */
/* .card:hover:before {
  opacity: 1;
} */
/* .card:hover .info {
  opacity: 1;
  transform: translateY(0px);
} */
/* .card:before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  display: block;
  width: 100%;
  height: 100%;
  border-radius: 15px;
  background: rgba(0, 0, 0, 0.6);
  z-index: 2;
  transition: 0.5s;
  opacity: 0;
} */
/* .card img {
  width: 100%;
  height: 100%;
  -o-object-fit: cover;
     object-fit: cover;
  position: absolute;
  top: 0;
  left: 0;
  border-radius: 15px;
} */
/* .card .info {
  position: relative;
  width: 100%;
  z-index: 3;
  color: white;
  opacity: 0;
  transform: translateY(30px);
  transition: 0.5s;
} */
/* .card .info h1 {
  margin: 0px;
  text-align:right;
} */
/* .card .info p {
  letter-spacing: 1px;
  font-size: 200%;
  margin-top: 8px;
} */
/* .card .info .text2 {
  font-size: 150%;
} */
/* .card .info button {
  float: right;

  bottom:0;
  padding: 0.6rem;
  outline: none;
  border: none;
  border-radius: 3px;
  background: white;
  color: black;
  font-weight: bold;
  cursor: pointer;
  transition: 0.4s ease;
} */
/* .card .info button:hover {
  background: dodgerblue;
  color: white;
} */


</style>
