<template>
  <div class="container-fluid">
    <b-navbar toggleable="lg" variant="faded" type="light">
      <b-navbar-brand href="#">
        <img src="../assets/logo.png" alt="Kitten">
      </b-navbar-brand>
      <b-navbar-nav>
        <b-nav-item href="#">Designers</b-nav-item>
        <b-nav-item href="#">Womens</b-nav-item>
        <b-nav-item href="#">Mens</b-nav-item>
        <b-nav-item href="#">Kids</b-nav-item>
        <b-nav-item href="#">Home&Gifts</b-nav-item>
        <b-nav-item href="#">Beauty</b-nav-item>
        <b-nav-item href="#">Sale</b-nav-item>
      </b-navbar-nav>
       <b-navbar-nav class="ml-auto">
        <b-nav-form>
          <b-form-input size="sm" class="mr-sm-2" placeholder="Search"></b-form-input>
          <b-button size="sm" class="my-2 my-sm-0" type="submit">Search</b-button>
        </b-nav-form>
       </b-navbar-nav>
    </b-navbar>
  </div>
</template>

<script>
export default {
  name: 'Header',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
