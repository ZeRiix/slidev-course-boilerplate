<script setup lang="ts">
import { useFrontmatter } from "../composables/useFrontmatter";
import { useSlideAsset } from "../composables/useSlideAsset";

export interface VisualContentFrontmatter {
	kicker?: string;
	title?: string;
	image?: string;
	imageAlt?: string;
	imageCaption?: string;
	imageSide?: "left" | "right";
	imageFit?: "contain" | "cover";
	placeholder?: string;
}

const frontmatter = useFrontmatter<VisualContentFrontmatter>();
const image = useSlideAsset(() => frontmatter.value.image);
</script>

<template>
	<section class="course-slide course-visual course-light">
		<header class="course-header">
			<span class="course-kicker">{{ frontmatter.kicker || 'Concepts' }}</span>

			<h1>{{ frontmatter.title }}</h1>
		</header>

		<div
			class="course-visual__grid"
			:class="frontmatter.imageSide === 'left' ? 'course-visual__grid--image-left' : ''"
		>
			<article class="course-prose course-visual__content">
				<slot />
			</article>

			<figure class="course-visual__figure">
				<img
					v-if="image"
					class="course-visual__image"
					:class="frontmatter.imageFit === 'cover' ? 'course-visual__image--cover' : ''"
					:src="image"
					:alt="frontmatter.imageAlt || ''"
				/>

				<div
					v-else
					class="course-visual__placeholder"
				>
					<span>Capture à ajouter</span>

					<p>{{ frontmatter.placeholder || 'Ajouter une image ciblée pour illustrer la notion.' }}</p>
				</div>

				<figcaption v-if="frontmatter.imageCaption">
					{{ frontmatter.imageCaption }}
				</figcaption>
			</figure>
		</div>
	</section>
</template>
