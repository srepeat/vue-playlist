<!--1、模板 HTML结构-->
<template>
  <div id="home">
    <!--<img src="./assets/logo.png">-->
    	<!--v-on:子时间的Key值，有参数就要传递一个$event-->
    <app-header v-bind:title="title" v-on:changeTitle="updataTitle($event)"></app-header>
    <!--使用一个中间节点进行绑定参数 ，也就是将这个对象绑定过去,但是这个操作等于全局操作-->
    <users v-bind:users="users"></users>
    <app-footer v-bind:title="title"></app-footer>
  </div>
</template>

<!--2、行为 逻辑处理-->
<script>
//局部配置	
//引入外部模板
import HelloWorld from './HelloWorld'
import Users from  './Users'
import Header from './Header'
import Footer from './Footer'
export default {
  name: 'Home',
  data(){
  	return {
  		//title:"第一个VUE脚手架！嘿嘿"
  		users : [
     		/*{name:"Henry",job:"WEB开发",show:false},
     		{name:"Henry",job:"WEB开发",show:false},
     		{name:"Henry",job:"WEB开发",show:false},
     		{name:"Henry",job:"WEB开发",show:false},
     		{name:"Henry",job:"WEB开发",show:false},
     		{name:"Henry",job:"WEB开发",show:false},
     		{name:"Henry",job:"WEB开发",show:false},
     		{name:"Henry",job:"WEB开发",show:false},
     		{name:"Henry",job:"WEB开发",show:false},
     		{name:"Henry",job:"WEB开发",show:false},
     		{name:"Henry",job:"WEB开发",show:false},
     		{name:"Henry",job:"WEB开发",show:false}*/
     	],
     	title:"数据类型：String Int  Boolean"
  	}
  },
  methods:{
  		updataTitle(title){
  			this.title=title;
  		}
  },
  components:{
  	HelloWorld,
  	"users":Users,
  	"app-header":Header,
  	"app-footer":Footer
  },
  created(){
  	this.$http.get("http://jsonplaceholder.typicode.com/users").then((data)=>{
  		//console.log(data);
  		this.users = data.body;
  	})
  }
}
</script>

<!--3、样式 美化页面-->
<style scoped>
/*绑定ID属性
 */	
 h1{
 		color: plum;
 		text-align: center;
 		
 }
 
#app {
 
}
</style>
