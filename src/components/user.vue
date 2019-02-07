<template>
	 <div class="component">
	 	<h1>The user component</h1>
	 	<h1 v-local-highlight.delayed="'red'">23456</h1>
	 	<p v-highlight.delayed="'red'">I am an awesome user!!!</p>
	 	<button @click="changeName" >change name</button>
	 	<hr>
	 	<div class="row">
	 		 <div class="col-lg-6">
        <app-user-detail :UserAge="age" @Agewasch="age=$event"></app-user-detail>
	 		 </div>
	 		 <div class="col-lg-6">
         <app-user-edit :name="name1" :UserAge="age"></app-user-edit>
	 		 </div>
	 	</div>
	 </div>
</template>

<script type="text/javascript">
	import UserDetail from './userDetail.vue'
	import UserEdit from './userEdit.vue'

	export default{
		data : function(){
			return {
      name1: 'Aniket',
      age : '20'

		}
	},
  methods: {
  	changeName : function(){
  		this.name1 = 'Maharathi Karn'
  	},
  	change: function(){
  		this.name1 = 'Aniket'
  	}
  }
	,
		components: {
			'app-user-detail': UserDetail,
			'app-user-edit': UserEdit
		},
		directives: {
			'local-highlight': {
				bind(el, binding, vnode){
		    var delay = 0
		    if(binding.modifiers['delayed']){
			  delay = 3000;
		}
		setTimeout(()=>{
			if(binding.arg == 'backgroung'){
			el.style.backgroundColor= binding.value;
		}else{
			el.style.color = binding.value;
		}
		},delay)

	}
			}
		}
	}
</script>

<style type="text/css" scoped>
	div{
		background-color : lightblue;
	}
</style>
