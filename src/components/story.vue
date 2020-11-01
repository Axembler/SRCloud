<template>
	<div class="story-style">
		<span>
			{{story_data.time}}
		</span>
		<span>
			{{story_data.text}}
		</span>
	</div>
</template>

<script>
export default {
	props:{
		story_data: {
			type: Object,
			default(){
				return{}
			}
		}
	}
}
	
</script>

<style>
.story-style{
	display: flex;
	flex-direction: column;
	align-items: flex-start;
	justify-content: space-between;
	margin-top: 30px;
	border: 1px solid #D7D3D3;
	border-radius: 10px;
	padding: 15px;
	color: #959595;
}
</style>