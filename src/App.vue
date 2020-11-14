<template>
	<div id="app-main">
		<div class="header">
			<img class="logo" src="./assets/Group12.png">
			<div class="search-bar">
				<input class="input" placeholder="Найти сервер">
				<img src="./assets/Vector4.png">
			</div>
			<div class="serversEtc">
				<div :class="{active:isServers}" @click="toServers" class="DserversEtc filter">
					Сервера
				</div>

				<div :class="{active:isTeams}" @click="toTeams" class="DserversEtc filter">
					Команды
				</div>

				<div :class="{active:isProjects}" @click="toProjects" class="DserversEtc filter">
					Проекты
				</div>
				<img class="filter-icon-group29" src="./assets/Group29.png">
				<img class="filter-icon-group21" src="./assets/Group21.png">
			</div>
		</div>

		<vServers v-if="isServers"></vServers>
		<vTeams v-if="isTeams"></vTeams>
		<vProjects v-if="isProjects"></vProjects>
	</div>
</template>

<script>
import vServers from './components/to-servers.vue'
import vTeams from './components/to-teams.vue'
import vProjects from './components/to-projects.vue'
export default{
	data(){
		return{
			isServers: true,
			isTeams: false,
			isProjects: false,
		}
	},
	name: 'App',
	components: {vServers, vTeams, vProjects},
	methods: {
		toServers(){
			this.isServers= true
			this.isTeams= false
			this.isProjects= false
		},
		toTeams(){
			this.isServers= false
			this.isTeams= true
			this.isProjects= false
		},
		toProjects(){
			this.isServers= false
			this.isTeams= false
			this.isProjects= true
		}
	}
}
</script>

<style>
::-webkit-scrollbar {
	width: 5px;
	height: 30px;
} 
::-webkit-scrollbar-thumb {
	border-radius: 10px;
	background-color: rgba(0, 163, 255, .7);
}
@font-face {
    font-family: 'Gotham Pro';
    src: url('assets/fonts/GothamPro-Bold.ttf');
    font-weight: bold;
    font-style: normal;
}
@font-face {
    font-family: 'Gotham Pro';
    src: url('assets/fonts/GothamPro.ttf');
    font-weight: normal;
    font-style: normal;
}
*{
	margin: 0px;
	padding: 0px;
	box-sizing: border-box;
	font-family: 'Gotham Pro';
}
body{
	width: 100%;
	background-color: #F7FAFF;
}
#app-main{
	margin: 0px auto;
	width: 100%;
	max-width: 1750px;
	display: flex;
	flex-direction: column;
	padding: 0px 15px;
}
.header{
	margin-top: 30px;
	display: flex;
	flex-direction: row;
	align-items: center;
	justify-content: space-between;
}
.frame-up, .frame-base{
	display: flex;
	flex-direction: row;
}
.input{
	width: 500px;
	height: 50px;
	background: #F2F6FE;
	border-radius: 15px;
	border: 0px;
	font-family: 'Gotham Pro';
	font-size: 16px;
	padding: 0px 60px 0px 20px;
	letter-spacing: .04em;
	color: rgba(0, 0, 0, .7);
}
.serversEtc{
	display: flex;
	flex-direction: row;
	font-size: 18px;
	color: #006DA9;
	align-items: center;
}
.DserversEtc{
	margin-left: 25px;
}
.filter-icon-group29{
	margin-left: 25px;
	width: 30px;
	height: 30px;
}
.filter-icon-group21{
	margin-left: 25px;
	width: 62px;
	height: 62px;
}
.search-bar{
	position: relative;
	align-items: center;
	justify-content: center;
	display: flex;
}
.search-bar img{
	position: absolute;
	right: 20px;
}
</style>