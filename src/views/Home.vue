<template>
	<div>
		<ProgressNow/>
		<div class="line">
			<h3> ラインアット　</h3>
		</div>
	</div>
</template>

<script>
// @ is an alias to /src
import ProgressNow from '@/components/home/index'

export default {
  name: 'home',
  components: {
    ProgressNow
  },
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
#about{
	img{
		width:80%
	}
}
</style>
