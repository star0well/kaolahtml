<template>
	<template v-for="(item, index) in data[currentIndex]" :key="index">
		<div>{{ item }}</div>
		{{ currentIndex }}
	</template>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
	props: {
		data: {
			type: Array,
			require: true
		},
		currentIndex: {
			type: Number,
			default: 0
		}
	},
	setup() {
		return {};
	}
});
</script>

<style scoped lang="less"></style>
