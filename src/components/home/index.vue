<template>
	<div class="progress-copmponent">
		<div class="top-header">
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
		<div class="plan">
			<div><h4>プラン</h4></div>
			<b-card :title="displayPlan(p.name)" v-for="p in plans" :key="p.name">
				<p class="card-text">
				{{p.description}}
				</p>
				<div>値段:{{p.price}}円</div>
				<div>応援人数{{p.num}}人</div>
		</b-card>
		</div> 
	</div>
</template>
<script>
export default {
  data () {
    return {
      goal:50000,
      plans:[{
      	name:"first",
      	description:"写真のみ",
      	price:500,
      	num:0,
      },
      {
      	name:"second",
      	description:"写真と言葉。本プレゼント",
      	price:800,
      	num:1,
      },
      {
      	name:"third",
      	description:"写真と言葉と本プレゼント、最後に名前",
      	price:1000,
      	num:0,
      }]
    }
  },
  computed:{
  	now(){
  		let sum = 0
  		for (let i = 0;i<this.plans.length;i++){
  			sum += (this.plans[i].price * this.plans[i].num)
  		}
  		return sum
  	},
  	allNum(){
  		let sum = 0
  		for (let i = 0;i<this.plans.length;i++){
  			sum += this.plans[i].num
  		}
  		return sum
  	}
  },
  methods: {
    progress() {
    	return 100 * this.now /this.goal 
    },
    displayPlan(str){
  		return str+"プラン"
  	},
  }
}
</script>
<style lang="scss" scoped>
@media screen and (max-width:600px) { 
	.progress-copmponent{
		.top-header{
			.topimg{
				img{
					width:90vw;
				}
			}
			.prog{
				margin-top:3em;
				.pp{
					font-weight:bold;
					font-size:30px;
				}
				.goal-price{
					font-size:1em;
					right:20%;
				}
			}
		}
		.plan{
			margin-top:2rem;
		}
	}
}
@media screen and (min-width:601px) { 
	.progress-copmponent{
		.top-header{
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
		.plan{
			margin-top:2rem;
		}
	}
}
</style>