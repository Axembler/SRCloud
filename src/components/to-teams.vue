<template>
	<div class="align_t">
		<div class="teams-top">
			<div class="teams-heading">
				<h2>
					Команды
				</h2>&nbsp;
				<div>
					<img class="filter-icon" src="../assets/Group60.png">
				</div>
			</div>
			<div class="filters">
				<div class="filter" :class="{active:isDevOps}" @click="isDevOps=!isDevOps; isFlutter=false; isGoLang=false; isPython=false; isDjango=false; isJavaScript=false; isPHP=false; filter='DevOps'; test()">
					<img class="filter-icon-teams" src="../assets/DevOps.png">
					<span>&nbsp;DevOps</span>
				</div>
				<div class="filter" :class="{active:isFlutter}" @click="isFlutter=!isFlutter; isDevOps=false; isGoLang=false; isPython=false; isDjango=false; isJavaScript=false; isPHP=false; filter='Flutter'; test()">
					<img class="filter-icon-teams" src="../assets/Flutter.png">
					<span>&nbsp;Flutter</span>
				</div>
				<div class="filter" :class="{active:isGoLang}" @click="isGoLang=!isGoLang; isDevOps=false; isFlutter=false; isPython=false; isDjango=false; isJavaScript=false; isPHP=false; filter='GoLang'">
					<img class="filter-icon-teams" src="../assets/GoLang.png">
					<span>&nbsp;GoLang</span>
				</div>
				<div class="filter" :class="{active:isPython}" @click="isPython=!isPython; isDevOps=false; isGoLang=false; isFlutter=false; isDjango=false; isJavaScript=false; isPHP=false; filter='Python'">
					<img class="filter-icon-teams" src="../assets/Python.png">
					<span>&nbsp;Python</span>
				</div>
				<div class="filter" :class="{active:isDjango}" @click="isDjango=!isDjango; isDevOps=false; isGoLang=false; isPython=false; isFlutter=false; isJavaScript=false; isPHP=false; filter='Django'">
					<img class="filter-icon-teams" src="../assets/Django.png">
					<span>&nbsp;Django</span>
				</div>
				<div class="filter" :class="{active:isJavaScript}" @click="isJavaScript=!isJavaScript; isDevOps=false; isGoLang=false; isPython=false; isDjango=false; isFlutter=false; isPHP=false; filter='JavaScript'">
					<img class="filter-icon-teams" src="../assets/JavaScript.png">
					<span>&nbsp;JavaScript</span>
				</div>
				<div class="filter" :class="{active:isPHP}" @click="isPHP=!isPHP; isDevOps=false; isGoLang=false; isPython=false; isDjango=false; isJavaScript=false; isFlutter=false; filter='PHP'">
					<img class="filter-icon-teams" src="../assets/PHP.png">
					<span>&nbsp;PHP</span>
				</div>
				<div class="filter">
					<img class="filter-icon" src="../assets/Group52.png">
				</div>
			</div>
		</div>
		<div class="teams">
		<team
			v-for="team in teamsByAreas"
			:key="team.team_number"
			:team_data="team"
		></team>
		</div>
		<div class="rating">
			<div class="align-icon">
				<img src="../assets/Vector3.png">
				<h3>&nbsp;Рейтинг</h3>
			</div>
			<div class="main-rating">
				<rating
				v-for="rating in ratings"
				:key="rating.team_number"
				:rating_data="rating"
				></rating>
			</div>
			<div class="frog"></div>
		</div>
	</div>
</template>

<script>
import team from './team.vue'
import rating from './rating.vue'
export default {
	data(){
		return {
			isDevOps: false,
			isFlutter: false,
			isGoLang: false,
			isPython: false,
			isDjango: false,
			isJavaScript: false,
			isPHP: false,
			filter: '',
			teams:[
			{
				team_number: '1',
				implement: ['Backend', 'Frontend'],
				members:[
					{
						name: 'Oleg Kovalenko',
						role: ['Teamlead','Frontend']
					},
					{
						name: 'Chuvinov Yaroslav',
						role: ['Fullstack']
					}
				],
				areas: ['GoLang', 'JavaScript', 'PHP'],
				team_img: ['Team1']
			},
			{
				team_number: '2',
				implement: ['Frontend', 'Backend', 'DevOps'],
				members:[
					{
						name: 'Oleg Kovalenko',
						role: ['Teamlead','Frontend']
					},
					{
						name: 'Chuvinov Yaroslav',
						role: ['Fullstack']
					},
				],
				areas: ['DevOps', 'JavaScript', 'PHP'],
				team_img: ['Team2']
			},
			{
				team_number: '3',
				implement: ['Neuronists'],
				members:[
					{
						name: 'Ilya Kulkin',
						role: ['Teamlead','Frontend']
					},
					{
						name: 'Chuvinov Yaroslav',
						role: ['Fullstack']
					}
				],
				areas: ['Python'],
				team_img: ['Team3']
			},
			{
				team_number: '4',
				implement: ['Frontend', 'Backend'],
				members:[
					{
						name: 'Oleg Kovalenko',
						role: ['Teamlead','Frontend']
					},
					{
						name: 'Chuvinov Yaroslav',
						role: ['Fullstack']
					}
				],
				areas: ['Django', 'JavaScript'],
				team_img: ['Team4']
			},
			{
				team_number: '5',
				implement: ['Frontend', 'Backend'],
				members:[
					{
						name: 'Oleg Kovalenko',
						role: ['Teamlead','Frontend']
					},
					{
						name: 'Chuvinov Yaroslav',
						role: ['Fullstack']
					}
				],
				areas: ['JavaScript', 'PHP'],
				team_img: ['Team5']
			},
			{
				team_number: '6',
				implement: ['iOS', 'Android'],
				members:[
					{
						name: 'Oleg Kovalenko',
						role: ['Teamlead','Frontend']
					},
					{
						name: 'Chuvinov Yaroslav',
						role: ['Fullstack']
					}
				],
				areas: ['Flutter'],
				team_img: ['Team6']
			}
			],
			ratings:[
			{
				team_number: '1',
				closed_card: '15',
				expired_card: '1',
				commits: '12'
			},
			{
				team_number: '2',
				closed_card: '13',
				expired_card: '4',
				commits: '16'
			},
			{
				team_number: '3',
				closed_card: '11',
				expired_card: '6',
				commits: '11'
			},
			{
				team_number: '4',
				closed_card: '19',
				expired_card: '0',
				commits: '1'
			},
			{
				team_number: '5',
				closed_card: '18',
				expired_card: '1',
				commits: '6'
			},
			{
				team_number: '6',
				closed_card: '13',
				expired_card: '2',
				commits: '8'
			}
			]
		}
	},
	name: 'to-teams',
	components: {team, rating},
	computed:{
		teamsByAreas(){
			return this.teams
		}
	}
	// Сортировка по картинкам
	// methods:{
	// 	test(){
	// 		let filtered = []
	// 		this.teams.forEach((item) => {
	// 			console.log(item.areas)
	// 		})
	// 		return filtered
	// 	}
	// }
}
</script>

<style>
.teams{
	display: flex;
	align-items: center;
	max-width: 80%;
	flex-wrap: wrap;
}
.grid-template-columns: {
	display: flex;
	align-items: center;
	max-width: 80%;
	flex-wrap: wrap;
}
.align_t{
	display: flex;
	justify-content: space-between;
	flex-direction: row;
	flex-wrap: wrap;
}
.teams-top{
	margin: 20px 0px;
	width: 100%;
	display: flex;
	justify-content: space-between;
	max-width: 80%;
}
.filter-icon-teams{
	height: 14px;
}
.rating{
	display: flex;
	flex-wrap: wrap;
	justify-content: space-between;
	align-items: center;
	max-width: 20%;
	height: 100%;
	position: relative;
}
.main-rating{
	max-height: 640px;
	overflow-y: scroll;
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: space-between;
	padding-right: 40px;
}
.frog{
	position: absolute;
	width: 100%;
	height: 100px;
	background: linear-gradient(to top, #F7FAFF, transparent);
	bottom: 0px;
	pointer-events: none;
}
</style>