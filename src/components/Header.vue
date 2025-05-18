<script setup lang="ts">
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import { faGithub } from '@fortawesome/free-brands-svg-icons';

</script>
<template>
	<header class="absolute inset-x-0 top-0 z-50">
		<nav class="flex items-center justify-between p-6 lg:px-8" aria-label="Global">
			<div class="flex lg:flex-1">
				<a href="#" class="-m-1.5 p-1.5">
					<span class="sr-only">Your Company</span>
					<img class="h-8 w-auto" src="/favicon.webp" alt="">
				</a>
			</div>
			<div class="flex flex-1 justify-end">
				<a href="https://github.com/isaiahpaget/freenutritionlabels" class=" text-2xl font-bold text-gray-900">
					<FontAwesomeIcon :icon="faGithub" />
				</a>
			</div>
		</nav>
	</header>
</template>
