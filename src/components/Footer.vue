<template>
	<footer>
		<p>{{title1}}{{title}}</p>
	</footer>
</template>

<script>
	export default {
  name: 'app-footer',
  props:{
  	title:{
  		type:String
  	}
  },
  data () {
    return {
    	title1:"Copyright 2019 vue demo "
    }
  }
}
	
</script>

<style scoped>
	footer{
		background: #222;
		padding: 10px;
	}
	
	p{
		color:lightgreen;
		text-align: center;
	}
	
</style>