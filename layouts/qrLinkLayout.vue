<script setup lang="ts">
import { useFrontmatter } from "../composables/useFrontmatter";

export interface QrFrontmatter {
	kicker?: string;
	title?: string;
	qr?: string;
	url?: string;
	caption?: string;
}

const frontmatter = useFrontmatter<QrFrontmatter>();
</script>

<template>
	<section class="course-slide course-qr course-dark">
		<header class="course-header course-header--center">
			<span class="course-kicker">{{ frontmatter.kicker || 'Resource' }}</span>

			<h1>{{ frontmatter.title }}</h1>

			<p v-if="frontmatter.caption">
				{{ frontmatter.caption }}
			</p>
		</header>

		<main class="course-qr__body">
			<img
				class="course-qr__image"
				:src="frontmatter.qr || '/assets/qr-code.svg'"
			/>

			<a
				class="course-qr__link"
				:href="frontmatter.url"
				target="_blank"
			>{{ frontmatter.url }}</a>
		</main>
	</section>
</template>
