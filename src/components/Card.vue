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

        this.cards = res.data.hits.slice(0, 16);
        console.log(this.result)

      } catch(error) {
        console.error(error)
      }
    },
}
</script>

<template>
  <div class="container" v-for="(value, index) in cards" :key="index">
    <div class="imgContainer">
      <img class="img" :alt="value.user" :src="value.largeImageURL" />
      <p class="tags">{{value.tags}}</p>
    </div>
    <div class="cardBottom">
      <div class="likesCon">
        <div class="heartIcon">
          <div class="heart1" />
          <div class="heart2" />
          <div class="heart3" />
        </div>
        <p class="txt">{{value.likes}}</p>
      </div>
      <div class="commentsCon">
        <div class="commentsIcon">
        </div>
        <p class="txt">{{value.comments}}</p>
      </div>
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
.container {
  padding: 10px;
  margin: 10px auto;
  background-color: rgb(163, 154, 154);
  box-shadow: 5px 5px 15px coral;
  border-radius: 15px;
  height: 350px;
  width: 250px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
.imgContainer {
  width: 0px;
}
  .img {
    width: 250px;
    border-radius: 10px;

  }

  .likesCon {
    display: flex;
    align-items: center;
    width: 100px;
  }
  .heartIcon {
    width: 30px;
    height: 30px;
    margin-right: 5px;
    display: flex;
    justify-content: center;
    position: relative;
  }
  .heart1 {
    width: 15px;
    height: 15px;
    background-color: crimson;
    border-radius: 50% 50% 0 50%;
  }
  .heart2 {
    background-color: crimson;
    width: 15px;
    height: 15px;
    border-radius: 50% 50% 50% 0;
  }
  .heart3 {
  background-color: crimson;
  width: 15px;
  height: 15px;
  position: absolute;
  bottom: 8px;
  transform: rotate(45deg);
  border-radius: 50% 0 0 0;
  }

  .commentsCon{
    display: flex;
    align-items: center;
  }
  .commentsIcon {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-evenly;
    width: 30px;
    height: 30px;
    margin-right: 5px;
    background-color: lightgreen;
    border-radius: 50% 50% 50% 0;
  }
</style>