<template>
	<div class="main_team">
		<div class="box_team">
			<div class="cont-mini-icon">
				<img class="mini-icon" v-for="(area, index) in team_data.areas" :key="index" :src="require(`../assets/${area}.png`)">
			</div>
			<img class="team-icon" v-for="(img, index) in team_data.team_img" :key="index" :src="require(`../assets/${img}.png`)">
			<span class="style-black">Команда {{team_data.team_number}}</span>
			<div class="cont-imps">
				<span class="style-gray align-imps" v-for="(imp, index) in team_data.implement" :key="index">{{imp}}</span>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	data(){
		return{}
	},
	name:'team',
	props:{
		team_data: {
			type: Object,
			default(){
				return{}
			}
		}
	}
}

</script>

<style>
.main_team{
	display: flex;
	justify-content: left;
	align-items: center;
	flex-direction: row;
}
.box_team{
	align-items: center;
	margin: 30px;
	padding: 10px;
	display: flex;
	flex-direction: column;
	width: 220px;
	height: 280px;
	background: #F2F6FE;
	box-shadow: 0px 0px 15px rgba(0, 0, 0, 0.15);
	border-radius: 10px;
	justify-content: space-between;
}
.mini-icon{
	width: 16px;
	padding: 5px;
	border-radius: 50%;
	border: 1px solid #C8C8C8;
	box-sizing: content-box;
	margin-left: 8px;
	height: 16px;
	object-fit: contain;
	filter: grayscale(100%);
	opacity: .6;
}
.team-icon{
	width: 125px;
	padding: 5px;
	border-radius: 50%;
	margin-left: 8px;
	border: 4px solid white;
	box-shadow: 0px 0px 0px 3px #00A3FF;
}	
.cont-mini-icon{
	display: flex;
	justify-content: flex-end;
	align-items: center;
	width: 100%;
}
.cont-imps{
	display: flex;
	justify-content: center;
	align-items: center;
	flex-wrap: wrap;
}
.cont-imps span{
	margin: 0px 4px;
}
.align-imps{
	padding-bottom: 8px;
}
</style>