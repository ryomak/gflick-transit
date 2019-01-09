<template>
	<div class="progress-copmponent">
		<div class="topimg">
			<img src="@/assets/top.png" />
		</div> 
		<div class="prog">
			<div>
				<h5>現在の支援額</h5>
				<div class="pp">{{now}}円</div>
				<b-progress :value="now" :max="goal" animated></b-progress>
				<span class="goal-price">目標金額は{{goal}}円</span>
			</div>
			<div>
				<h5>応援してくれている人</h5>
				<div class="pp">{{allNum}}人</div>
			</div>
			<div>
				達成率
				<div class="pp"> {{progress()}} %</div>
				
			</div>
		</div>
	</div>
</template>
<script>
export default {
  data () {
    return {
      goal:50000,
      first:{
      	price:500,
      	num:0,
      },
      second:{
      	price:800,
      	num:1,
      },
      third:{
      	price:1000,
      	num:0,
      },
    }
  },
  computed:{
  	now(){
  		return (this.first.price * this.first.num) + (this.second.price * this.second.num) + (this.third.price * this.third.num)
  	},
  	allNum(){
  		return this.first.num+this.second.num+this.third.num
  	}
  },
  methods: {
    progress() {
    	return 100 * this.now /this.goal 
    }
  }
}
</script>
<style lang="scss" scoped>
@media screen and (min-width:600px) { 
	.topimg{
		img{
			width:90vw;
		}
	}
}

.progress-copmponent{
	display:flex;
	.topimg{
		img{
			width:50vw;
		}
	}
	.prog{
		margin-left:3em;
		.pp{
			font-weight:bold;
			font-size:30px;
		}
		.goal-price{
			font-size:0.5em;
			right:20%;
		}
	}
}
</style>