<template>
	<div class="align_s">
		<div class="servers-top">
			<div class="servers-heading">
				<h2>
					Сервера
				</h2>&nbsp;
				<div>
					<img class="filter-icon" src="../assets/Group60.png">
				</div>
			</div>
			<div class="filters">
				<div class="filter" :class="{active:isOnline}" @click="isOnline=!isOnline; isOffline=false">
					<div class="circle-green"></div>&nbsp;Online
				</div>
				<div class="filter" :class="{active:isOffline}" @click="isOffline=!isOffline; isOnline=false">
					<div class="circle-red"></div>&nbsp;Offline
				</div>
				<div class="filter" :class="{active:isDocker}" @click="isDocker=!isDocker">
					<img src="../assets/Docker.png">&nbsp;Docker
				</div>
				<div class="filter">
					<img class="filter-icon" src="../assets/Group52.png">
				</div>
			</div>
		</div>
		<div class="servers">
			<server
				v-for="server in filterServers"
				:key="server.ip"
				:server_data="server"
			></server>
		</div>
		<div class="story">
			<h3>История</h3>
			<div class="main-story">
				<story
				v-for="story in stories"
				:key="story.time"
				:story_data="story"
			></story>
			</div>
			<div class="frog"></div>
		</div>
	</div>
</template>

<script>
import server from './server.vue'
import story from './story.vue'
export default {
	data(){
		return {
			isOnline: false,
			isOffline: false,
			isDocker: false,
			servers:[
			{
				status: true,
				ip: '10.0.0.112',
				domains:['исгу.рф', 'portal.admlr.lipetsk.ru']
			},
			{
				status: false,
				ip: '10.0.0.112',
				domains:['исгу.рф', 'portal.admlr.lipetsk.ru']
			},
			{
				status: true,
				ip: '10.0.0.112',
				domains:['исгу.рф', 'portal.admlr.lipetsk.ru']
			},
			{
				status: true,
				ip: '10.0.0.112',
				domains:['исгу.рф', 'portal.admlr.lipetsk.ru']
			},
			{
				status: true,
				ip: '10.0.0.112',
				domains:['исгу.рф', 'portal.admlr.lipetsk.ru']
			},
			{
				status: false,
				ip: '10.0.0.112',
				domains:['исгу.рф', 'portal.admlr.lipetsk.ru']
			},
			{
				status: true,
				ip: '10.0.0.112',
				domains:['исгу.рф', 'portal.admlr.lipetsk.ru']
			},
			{
				status: false,
				ip: '10.0.0.112',
				domains:['исгу.рф', 'portal.admlr.lipetsk.ru']
			},
			{
				status: false,
				ip: '10.0.0.112',
				domains:['исгу.рф', 'portal.admlr.lipetsk.ru']
			},
			],
			stories:[
			{
				time: '14:88',
				text: 'Пыжилая анаконда изменил Dockerfile'
			},
			{
				time: '13:24',
				text: 'Олег “Деда” Коваленко послал в docker мем'
			},
			{
				time: '01:14',
				text: 'Олег “Деда” Коваленко послал в docker мем'
			},
			{
				time: '15:28',
				text: 'Олег “Деда” Коваленко послал в docker мем'
			},
			{
				time: '16:19',
				text: 'Олег “Деда” Коваленко послал в docker мем'
			},
			{
				time: '23:10',
				text: 'Олег “Деда” Коваленко послал в docker мем'
			},
			{
				time: '20:31',
				text: 'Олег “Деда” Коваленко послал в docker мем'
			},
			]
		}
	},
	name: 'to-servers',
	components: {server, story},
	computed: {
		filterServers(){
			if (this.isOnline && !this.isOffline) {
				return this.servers.filter(server => server.status === true)
			} else if (!this.isOnline && this.isOffline) {
				return this.servers.filter(server => server.status === false)
			}
			return this.servers
		}
	}
}
</script>

<style>
.servers{
	display: flex;
	align-items: center;
	max-width: 80%;
	flex-wrap: wrap;
	justify-content: flex-start;
	height: 100%;
}
.align_s{
	display: flex;
	justify-content: space-between;
	flex-direction: row;
	flex-wrap: wrap;
}
.servers-top{
	margin: 20px 0px;
	width: 100%;
	display: flex;
	justify-content: space-between;
	max-width: 80%;
	align-items: center;
}
.filters{
	display: flex;
	align-items: center;
}
.filter{
	margin: 0px 10px;
	display: flex;
	align-items: center;
	padding-bottom: 5px;
	border-bottom: 2px solid transparent;
	user-select: none;
	cursor: pointer;
}
.active{
	border-bottom: 2px solid #00A3FF;
}
h2{
	font-size: 48px;
	color: #00A3FF;
}
h3{
	font-size: 34px;
	color: #1D1E1F;
}
.filter-icon{
	width: 23px;
	height: 23px;
}
.story{
	display: flex;
	flex-wrap: wrap;
	justify-content: space-between;
	align-items: center;
	max-width: 20%;
	height: 100%;
	position: relative;
	padding-left: 50px;
}
.main-story{
	max-height: 620px;
	overflow-y: scroll;
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: space-between;
	padding-right: 40px;
}
</style>