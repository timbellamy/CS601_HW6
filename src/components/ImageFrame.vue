<script>
import list from '@/models/imageData.json'
export default {
  data() {
    return {
      imageList: list,
      imagePair: list[0],
      currentImg: list[0][0],
      currentIndex: 0,
    };
  },
  methods: {
    update: function (updateImage) {
      if (updateImage) {
        this.currentImg = this.imagePair[1];
      } else {
        this.currentImg = this.imagePair[0]
      }
    },
    nextImage: function () {
      if (this.imageList.length === (this.currentIndex += 1)){
        this.currentIndex = 0;
      }

      this.imagePair = this.imageList[this.currentIndex];
      this.currentImg = this.imagePair[0];
    },
    prevImage: function (){
      if ((this.currentIndex -= 1) < 0){
        this.currentIndex = (this.imageList.length - 1);
      }

      this.imagePair = this.imageList[this.currentIndex];
      this.currentImg = this.imagePair[0];
    }
  }
}
</script>

<template>
  <div class="container">
    <h2>{{ currentImg.name }}</h2>
    <p>Image source: <cite>{{ currentImg.credit }}</cite></p>
    <img :src="require(`@/assets/${ currentImg.src }`)"
         @mouseover="update(true)"
         @mouseleave="update(false)" alt="">

    <div class="btn_group">
      <button @click="prevImage()">Prev</button>
      <button @click="nextImage()">Next</button>
    </div>
  </div>
</template>

<style scoped>
.container{
  display: flex;
  flex-flow: column wrap;
  align-content: center;
  justify-content: center;
  width: 100vw;
  height: 100vh;
}
img{
  width: 50vw;
  border: 1px solid black;
  border-radius: 10px;
}
.btn_group{
  margin-top: 10px;
}
button{
  margin-left: 15px;
  padding: 5px 20px 5px 20px;
  border-radius: 10px;
}
</style>