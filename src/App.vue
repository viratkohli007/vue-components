<template>
  <div id="app">
    <app-user></app-user>
  </div>
</template>

<script>
  import user from './components/user.vue'
export default {
     components: {
       'app-user': user
     }
}
</script>

<style type="text/css" >
  div.component {
    border: 1px solid black;
    padding: 30px;
    margin: 30px;

  }
</style>
