<template>
	<div class="conts-cards">
		<div class="cont-ratings">
			<img class="team-face" src="../assets/Team1.png">
			<!-- <img class="team-icon" v-for="(img, index) in team_data.team_img" :key="index" :src="require(`../assets/${img}.png`)"> -->
			<div class="rating-cards">
				<span class="rating-style">
					Команда {{rating_data.team_number}}
				</span>
				<span class="rating-style-small">
					<img class="rating-img" src="../assets/Vector-4.png">						
					{{rating_data.closed_card}} Карточек закрыто
				</span>
				<span class="rating-style-small">
					<img class="rating-img" src="../assets/Vector-5.png">
					{{rating_data.expired_card}} Карточек просрочено
				</span>
				<span class="rating-style-small">
					<img class="rating-img" src="../assets/Group72.png">
					{{rating_data.commits}} Коммиты
				</span>
			</div>
		</div>
		<div class="line"></div>
	</div>
</template>

<script>
export default {
	data(){
		return{}
	},
	name:'rating',
	props:{
		rating_data: {
			type: Object,
			default(){
				return{}
			}
		}
	}
}
	
</script>

<style>
.rating-cards{
	display: flex;
	flex-direction: column;
}
.team-face{
	margin-left: 5px;
	width: 100px;
	border: 4px solid white;
	border-radius: 50%;
	margin-right: 20px;
	box-shadow: 0px 0px 0px 3px orange;
}
.rating-style-small{
	font-size: 12px;
	margin-bottom: 5px;
	display: flex;
	align-items: center;
}
.rating-style{
	font-size: 18px;
	font-weight: bold;
	margin-bottom: 5px;
	display: flex;
	align-items: center;
}
.rating-img{
	width: 18px;
	margin-right: 5px;
}
.line{
	margin-top: 15px;
	background-color: #E0E0E0;
	height: 2px;
	width: 100%;
}
.conts-cards{
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: space-between;
	margin-top: 30px;
}
.cont-ratings{
	display: flex;
	align-items: center;
	justify-content: center;
}
</style>