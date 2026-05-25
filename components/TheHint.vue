<script setup lang="ts">
withDefaults(defineProps<{
	title?: string;
}>(), {
	title: "Hint",
});
</script>

<template>
	<aside class="course-hint">
		<strong>{{ title }}</strong>

		<div>
			<slot />
		</div>
	</aside>
</template>
