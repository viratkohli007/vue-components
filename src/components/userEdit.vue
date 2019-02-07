<template>
	 <div>
	 	<h1>You may Edit the user detail here</h1>
	 	<p>Edit me</p>
    <p>user name: {{ name }}</p>
    <p>user Age: {{ UserAge }}</p>
    <button @click="change">changeIt</button>

	 </div>
</template>

<script type="text/javascript">

	import {eventBus} from '../main.js'

	export default {
       props: {name:{}, UserAge:{}},
		methods: {
			change(){
        this.name = 'Aniket'
        this.$emit('againch', this.name)
			}

		},
		created(){
       eventBus.$on('Agewasch', (age)=>{
       	this.UserAge = age;
       })
		}
	}
</script>

<style type="text/css" scoped>
	div{
    background-color: lightgreen;
    border: 1px solid black;
	}
</style>
