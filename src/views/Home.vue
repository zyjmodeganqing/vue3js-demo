<template>
	<div class="title">首页</div>
  <HelloWorld msg="大房间"></HelloWorld>
</template>

<script setup>
import HelloWorld from "@/components/HelloWorld.vue";
import { ref } from "vue";
const color = ref("red");
</script>

<style lang="scss" scoped>
.title {
	font-size: 30px;
	color: v-bind(color);
}
</style>
