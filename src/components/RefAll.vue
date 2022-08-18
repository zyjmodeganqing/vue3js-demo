<template>
	<div class="ref">
		<button @click="btnClick">查看是否是响应式数据</button>

		<div>{{ msg.name }}</div>
	</div>
</template>

<script setup>
import { ref, isRef, unref, shallowRef, triggerRef, customRef } from "vue";
console.log("执行");

const title = "是不是";

const show = ref(true);

let msg = shallowRef({
	name: "张三",
});

const btnClick = () => {
	console.log(isRef(title)); //false
	console.log(isRef(show)); //true

	//unref 如果参数是ref返回ref的值，否则返回参数本身 等同于val = isRef(val) ? val.value : val
	console.log(unref(title)); //是不是
	console.log(unref(show)); //true

	msg.value.name = "李四"; //这样做msg 的name是不会响应式变化的
	msg.value = { name: "王五" }; //这样才能使msg的name发生变化
	triggerRef(msg); //或者使用triggerRef强制刷新DOM也可以改变值
};
</script>

<style lang="scss" scoped>
.ref {
	margin-top: 20px;
}
</style>
