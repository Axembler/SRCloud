<template>
	<div class="box_server">
		<div class="align-ofnline" v-if="server_data.status">
			<span class="style-gray">IP-адрес:</span>
			<div class="align-ofnline2">
				<span class="style-gray-small">Online</span>&nbsp;
				<div class="circle-green"></div>
			</div>
		</div>
		<div class="align-ofnline" v-else>
			<span class="style-gray">IP-адрес:</span>
			<div class="align-ofnline2">
				<span class="style-gray-small">Offline</span>&nbsp;
				<div class="circle-red"></div>
			</div>
		</div>
		<span class="style-blue">{{server_data.ip}}</span>
		<span class="style-gray domain-width">Домены:</span>
		<div class="align-domains">
			<span class="domains-style" v-for="domain in server_data.domains" :key="domain">{{domain}}</span>
		</div>
		<div class="align-etc">
			<div>
				<span class="style-gray">Подробнее</span>&nbsp;
				<img class="filter-icon-arrow2" src="../assets/Arrow2.png">
			</div>
			<div class="align-etc2">
				<img class="filter-icon-vector2" src="../assets/Vector2.png">
			</div>
		</div>
	</div>
</template>

<script>
export default {
	data(){
		return{}
	},
	name:'server',
	props: {
		server_data: {
			type: Object,
			default(){
				return {}
			}
		}
	}
}
</script>

<style>
.box_server{
	margin: 0px 50px 30px 0px;
	display: flex;
	flex-wrap: wrap;
	justify-content: space-between;
	box-shadow: 0px 0px 20px rgba(0, 0, 0, 0.15);
	border-radius: 10px;
	padding: 20px;
	width: 400px;
	height: 200px;
	background: #F2F6FE;
}	
.style-blue{
	font-size: 26px;
	color: #00A3FF;
	width: 100%;
	font-weight: bold;
	margin-bottom: 10px;
}
.style-gray{
	color: #989898;
	font-size: 12px;
}
.style-gray-small{
	color: #989898;
	font-size: 9px;
}
.style-black{
	color: #000000;
	font-weight: bold;
	font-size: 18px;
	line-height: 17px;
}
.circle-green, .circle-red{
	width: 15px;
	height: 15px;
	border-radius: 50%;
}
.circle-green{
	background-color: #00CA69;
}
.circle-red{
	background-color: red;
}
.align-ofnline, .align-etc{
	display: flex;
	width: 100%;
	justify-content: space-between;
	align-items: center;
}
.align-ofnline2, .align-etc2, .teams-heading, .servers-heading, .align-icon{
	display: flex;
	align-items: center;
}
.filter-icon-arrow2{
	width: 14px;
}
.align-domains{
	margin-bottom: 10px;
}
.domains-style{
	font-weight: bold;
	display: flex;
}
.domain-width{
	width: 100%;
}
</style>