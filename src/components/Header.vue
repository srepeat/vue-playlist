<template class="header">
	<header v-on:click="changeHeander">
		<h1>{{title1}}{{title}}</h1>
	</header>
</template>

<script>
	export default {
  name: 'app-header',
  props:{
  	title:{
  		type:String
  	}
  },
  data () {
    return {
     	title1:"title 2019 vue demo"
    }
  },
  methods:{
  		changeHeander:function(){
  			//this.title="   changeHeader";
  			//子传值给父  使用$emit("模板绑定的事件名称","传递的数据")
  			this.$emit("changeTitle","子组件向父组件传递");
  		}
  }
}
	
</script>

<style scoped>
	header{
		background: lightgreen;
		padding: 10px;
	}
	
	h1{
		color: #222;
		text-align: center;
	}
</style>