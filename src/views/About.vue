<template>
  <div class="about">
    <h1>{{teamName}}</h1>
    <img src="@/assets/about_me.png" />
    <div> 
    	私たちは{{teamName}}です．
    </div>
  </div>
</template>
<script>
	export default{
		name:'About',
		computed:{
			teamName(){
				return 'Hangout'
			}
		}
	}
</script>
<style lang="scss" scoped>
$about-color:#DDDDDD;
$about-back:#64b587;
.about{
	img{
		width:80%
	}
}
</style>
