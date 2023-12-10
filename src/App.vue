<template>
<div class="header">
  <h1>Texas Skylines</h1>
  <image-frame/>
  <citation/>
</div>
</template>

<script>
import ImageFrame from "@/components/ImageFrame.vue";
import Citation from "@/components/citation.vue";

export default {
  name: 'App',
  components: {
    Citation,
    ImageFrame
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: flex;
  flex-flow: column wrap;
  align-items: center;
  justify-items: center;

}
#app-container{
  max-width: 100%;
  max-height: 100%;
}
</style>
