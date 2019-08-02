<template>
  <div class="container-fluid">
    <b-img id= "main-img" src="https://n.nordstrommedia.com/id/3853ecea-f2df-4918-ad59-5a39dd35f018.jpeg?w=1608&h=366" fluid alt="Sale"></b-img>
    <Recs></Recs>
  </div>

</template>

<script>
import Recs from './Recs.vue'

export default {
  name: 'Main',
  props: {
    msg: String
  },
  components: {
    Recs
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#main-img {
  padding-top: 10px;
  padding-bottom: 50px;
}
</style>
