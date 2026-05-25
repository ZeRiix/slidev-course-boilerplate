<script setup lang="ts">
defineProps<{
	value: string;
}>();
</script>

<template>
	<div class="course-duration">
		<span>Estimated duration</span>

		<strong>{{ value }}</strong>
	</div>
</template>
