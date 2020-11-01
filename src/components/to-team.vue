<template>
	<div>
		<h2>
			Команда{{team_data.team_number}}
		</h2>&nbsp;
		<div>
			<img class="filter-icon" src="../assets/Group60.png">
		</div>
		<div class="gitlab">
			<div class="align-icon">
				<img src="../assets/Group72.png">
				<h3>&nbsp;GitLab</h3>
			</div>
			<div>
		
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
	props: {
		team_data: {
			type: Object,
			default(){
				return {}
			}
		}
	}
}
	
</script>

<style>
.gitlab{
	max-width: 20%;
}
</style>