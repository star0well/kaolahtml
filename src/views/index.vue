<template>
	<div class="wrap">
		<div class="home" @scroll="handleScorll" ref="divRef">
			<page-header></page-header>
			<logo-search></logo-search>

			<page-content></page-content>

			<yc-show-data :scrollTop="scrollTop">
				<template #rNav><ycFixNav /> </template>
			</yc-show-data>
			<yc-show-data />
			<yc-show-data />
		</div>
	</div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import PageHeader from '@/components/nav-header';
import logoSearch from '@/components/logo-search';
import PageContent from '@/components/page-content';
import YcShowData from '@/base-ui/ycShowDaTA';
import ycFixNav from '@/base-ui/ycFixNav';

export default defineComponent({
	components: {
		PageHeader,
		logoSearch,
		PageContent,
		YcShowData,
		ycFixNav
	},
	setup() {
		const divRef = ref<HTMLElement>();
		const scrollTop = ref(0);
		const handleScorll = () => {
			console.log('滚动了');
			if (divRef.value) {
				scrollTop.value = document.documentElement.scrollTop;
				console.log(scrollTop.value);
			}
		};
		document.addEventListener('scroll', handleScorll);

		return { handleScorll, divRef, scrollTop };
	}
});
</script>

<style scoped>
.wrap {
	min-width: 700px;
	overflow-x: hidden;
}
</style>
