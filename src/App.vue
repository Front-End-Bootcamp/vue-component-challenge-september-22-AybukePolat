<script setup>
	import DATA from "../public/data/data.json"
	import {onMounted, ref} from "vue";
	import Group from "./components/Group.vue"
	import GroupMemberList from "./components/GroupMemberList.vue"

let groups = ref([])
let members = ref([])
let groupValue = ref([])
onMounted(() => {
	let groupsName = DATA.map(data => data.group)
	groups.value = [...new Set(groupsName)]
	console.log(groups.value);
})

function getGroupMembers(group) {
	members.value = DATA.filter(data => data.group === group)
	groupValue.value = group
}
</script>

<template>
	<div >
<Group :groups="groups" @getMembersForGroupName="getGroupMembers"></Group>


<GroupMemberList class="groupMember" :groupMembers="members" :group="groupValue"></GroupMemberList>
</div>
</template>

<style scoped>

</style>
