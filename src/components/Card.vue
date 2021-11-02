<script>
import axios from 'axios';
export default {
  data(){
    return {
      cards: [],
    };
  },
    async created() {
      try {
        const res = await axios.get('https://pixabay.com/api/?key=24139602-279077e1bba33438ab5b9b063&q=yellow+flowers&i');

        this.cards = res.data.hits.slice(0, 4);
        console.log(this.cards)

      } catch(error) {
        console.error(error)
      }
    },
    methods: {
      imgClick: function() {
        
      }
    }
}

</script>

<template>
  <div class="imgContainer" v-for="(value, index) in cards" :key="index">
    <img v-on:click="imgClick" class="img" alt="Vue logo" :src="value.largeImageURL" />
    <div class="cardBottom">
      <p class="txt">likes <span class="txt">{{value.likes}}</span></p>
      <p class="txt">comments <span class="txt">{{value.comments}}</span></p>
    </div>
  </div>
</template>

<style scoped>
.cardBottom {
  display: flex;
  justify-content: space-between;
}
.txt {
  color: black;
}
.imgContainer {
  padding: 10px;
  margin: 10px 0 0 0;
  background-color: rgb(255, 87, 87);
  border-radius: 15px;
  height: 400px;
  width: 350px;
}
  .img {
    width: 350px;
    border-radius: 10px;
  }
</style>