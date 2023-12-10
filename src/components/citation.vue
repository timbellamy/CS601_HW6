<script>
export default {
  data(){
    return {
      cite: `Salamon, J. (2023, January 17). See how Texas’s big-city skylines have changed over the past Half Century. Texas Monthly. https://www.texasmonthly.com/being-texan/texas-changing-skylines-big-cities-austin-dallas-houston-san-antonio/`,
      show: false
    }
  }
}

</script>

<template>
    <button @click="show = !show">Show Citation</button>
  <div class="citation">
      <p v-show="show"><cite>
        {{ cite }}
      </cite></p>
  </div>
</template>

<style scoped>
.citation{
  width: 50vw;
}
a{
  margin-left: 15px;
  padding: 5px 20px 5px 20px;
  border-radius: 10px;  border: 1px solid black;
}
</style>