<template>
	<div class="users">
		<ul >
			<!--v-on:click="user.show = !user.show"-->
			<li v-for="user in users">
				<h1>{{user.name}}</h1>
				<h2>{{user.email}}</h2>
			</li>
		</ul>
		<button v-on:click="deleteUsers">删除</button>
	</div>
</template>

<script>
	export default {
  name: 'User',
  //两种引用值方式 1==>可以使用props:传递的类型  2==>标准写法type:类型 required:该数组必须存在
  //props:["users"],
  props:{
  	users:{type:Array,
  		required:true}
  },
  data () {
    return {
     	
    }
  },
  methods:{
  	deleteUsers:function(){
  		//pop函数方法，是数据从栈中移除
  		this.users.pop();
  	}
  }
}
	
</script>

<style scoped>
	.users{
		width: 100%;
		max-width: 1200px;
		margin: 40px auto;
		padding: 0 20px;
		box-sizing: border-box;
	}
	
	ul {
		display: flex;
		flex-wrap: wrap;
		list-style-type: none;
		padding: 0;
	}
	
	li{
		flex-grow: 1;
		flex-basis: 200px;
		text-align: center;
		padding: 30px;
		border: 1px solid black;
		margin: 10px;
	}
	
</style>