<script setup>

	const props = defineProps(["groupMembers","group"])


</script>
<template>
	<div class="memberDiv">
		<span class="member" :style="[member.type != null ? {background:group}:{background: 'white'}]" v-for="member in groupMembers" >{{ member.name }}</span>
	</div>

</template>

<style scoped>
	span.member {
	
  display: inline-block; /* the default for span */
  width: 100px;
  height: 100px;
  padding: 15px;
  border: 2px solid black;  
	margin-left: 5px;
	float: left;
}
.memberDiv{
	margin-right: 100px;
	margin-left: 0px;
	padding: 20px,200px;
	justify-items: center;
	}
</style>