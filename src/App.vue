<!--1、模板 HTML结构-->
<template>
  <div id="app">
  		<ul>
  			<li><router-link to="/">Home</router-link></li>
  			<li><router-link to="/helloworld">HelloWorld</router-link></li>
  		</ul>
  	
    	<router-view></router-view>
  </div>
</template>

<!--2、行为 逻辑处理-->
<script>
//局部配置	
//引入外部模板
/*import HelloWorld from './components/HelloWorld'
import Users from  './components/Users'
import Header from './components/Header'
import Footer from './components/Footer'*/
export default {
  name: 'App',
  data(){
  	return {
  		
  	}
  }
}
</script>

<!--3、样式 美化页面-->
<style scoped>

 
#app {
 
}
</style>
