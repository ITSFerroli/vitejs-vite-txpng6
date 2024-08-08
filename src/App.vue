<script setup>
import { ref } from 'vue';
import VirtualScroller from 'primevue/virtualscroller';

const items = ref(Array.from({ length: 100000 }).map((_, i) => `Item #${i}`));

</script>

<template>
	<div class="flex justify-center">
		<VirtualScroller :items="items" :item-size="50"
			class="border border-surface-300 dark:border-surface-700 rounded-md" style="width: 200px; height: 200px">
			<template #item="{ item, options }">
				<div :class="['flex items-center p-2', { 'bg-surface-100 dark:bg-surface-700': options.odd }]"
					style="height: 50px">
					{{ item }}
				</div>
			</template>
		</VirtualScroller>
	</div>
</template>