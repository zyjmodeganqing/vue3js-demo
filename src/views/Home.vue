<template>
	<div :class="[isActive ? 'active' : 'other', 'title']">首页</div>
	<RefAll></RefAll>
	<HelloWorld msg="VUE3"></HelloWorld>
</template>

<script setup>
import HelloWorld from "@/components/HelloWorld.vue";
import RefAll from "@/components/RefAll.vue";
import { ref } from "vue";

const isActive = ref(true);
</script>

<style lang="scss" scoped>
.title {
	font-size: 30px;
}
.active {
	color: red;
}
.other {
	color: black;
}
</style>
