<template>
	 <div>
	 	<h1>You may view the user detail here</h1>
	 	<p>Many details</p>
    <p>user age {{UserAge}}</p>

    <button @click="editAge">Edit Age</button>

	 </div>
</template>

<script type="text/javascript">
  import {eventBus} from '../main.js'
  export default {
   props: {
    UserAge:{}
   },
   methods: {
    editAge(){
      this.UserAge = 21
      //this.$emit('Agewasch', this.UserAge)
     // eventBus.$emit('Agewasch', this.UserAge)
     eventBus.changeAge(this.UserAge)
    }
   }
  }
</script>

<style type="text/css" scoped>
	div{
    background-color: lightcoral;
    border: 1px solid black;
	}
</style>
