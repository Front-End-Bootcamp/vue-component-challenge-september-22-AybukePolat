<script setup>

	const props = defineProps(["groups"])
	const emits = defineEmits(["getMembersForGroupName"])
function memberAction(group){
	emits("getMembersForGroupName",group)
}

</script>
<template>
	<div class="groupDiv">
		<span class="group" :class="group" v-for="group in groups" @click="memberAction(group)" >{{group}}</span>
	</div>
</template>

<style scoped>
	span.group {
		
		margin-bottom: 50px;
  display: inline-flex; 
  width: 80px;
  height: 100px;
  padding: 25px;
  border: 2px solid black;  
	margin-left: 5px;
	justify-content: center;

}
.groupDiv{
	align-items: center;
	margin-bottom: 30px;
}
.Orchid {
	background-color: orchid;
}
.SteelBlue{
	background-color: steelblue;
}
.IndianRed{
	background-color: IndianRed;
}
.YellowGreen{
	background-color: yellowgreen;
}
.LightSeaGreen{
	background-color: LightSeaGreen;
}

</style>