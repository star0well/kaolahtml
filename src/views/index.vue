<template>
	<div>
		<page-header></page-header>
	</div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import PageHeader from '@/components/nav-header';

export default defineComponent({
	components: {
		PageHeader
	},
	setup() {
		return {};
	}
});
</script>

<style scoped></style>
