<script setup lang="ts">
import * as htmlToImage from 'html-to-image';
import Label from './components/Label.vue';
import Form from './components/Form.vue';
import { ref } from 'vue';
import type { Nutrition } from './types';

const nutrition = ref<Nutrition>({
	measurement: "",
	measurement_fr: "",
	measurement_metric: "",
	measurement_unit: "",
	// servings: "",

	calories: "",
	fats: "",
	fats_percent: "",
	saturated: "",
	saturated_percent: "",

	trans: "",

	carbs: "",

	fibre: "",
	fibre_percent: "",

	sugar: "",
	sugar_percent: "",

	protein: "",
	cholesterol: "",

	sodium: "",
	sodium_percent: "",

	potassium: "",
	potassium_percent: "",

	calcium: "",
	calcium_percent: "",

	iron: "",
	iron_percent: "",

	ingredients: "",
	ingredients_fr: "",
	may_contain: "",
	may_contain_fr: "",
	contains: "",
	contains_fr: ""
})
const handleChange = (nutrition_new: Nutrition) => {
	nutrition.value = nutrition_new
}
const onDownload = async () => {
	const node = document.getElementById('nutritionlabel')
	if (!node) {
		alert("An error has occured, try a take a screenshot")
		return
	}
	htmlToImage.toJpeg(node, { quality: 0.95 })
		.then(function (dataUrl) {
			var link = document.createElement('a');
			link.download = 'nutritionlabel.jpeg';
			link.href = dataUrl;
			link.click();
		});
}

</script>

<template>
	<div class="relative isolate overflow-hidden bg-white px-6 py-24 sm:py-32 lg:overflow-visible lg:px-0">
		<div class="absolute inset-0 -z-10 overflow-hidden">
			<svg class="absolute top-0 left-[max(50%,25rem)] h-[64rem] w-[128rem] -translate-x-1/2 [mask-image:radial-gradient(64rem_64rem_at_top,white,transparent)] stroke-gray-200"
				aria-hidden="true">
				<defs>
					<pattern id="e813992c-7d03-4cc4-a2bd-151760b470a0" width="200" height="200" x="50%" y="-1"
						patternUnits="userSpaceOnUse">
						<path d="M100 200V.5M.5 .5H200" fill="none" />
					</pattern>
				</defs>
				<svg x="50%" y="-1" class="overflow-visible fill-gray-50">
					<path
						d="M-100.5 0h201v201h-201Z M699.5 0h201v201h-201Z M499.5 400h201v201h-201Z M-300.5 600h201v201h-201Z"
						stroke-width="0" />
				</svg>
				<rect width="100%" height="100%" stroke-width="0" fill="url(#e813992c-7d03-4cc4-a2bd-151760b470a0)" />
			</svg>
		</div>
		<div
			class="mx-auto grid max-w-2xl grid-cols-1 gap-x-8 gap-y-16 lg:mx-0 lg:max-w-none lg:grid-cols-2 lg:items-start lg:gap-y-10">
			<div
				class="lg:col-span-2 lg:col-start-1 lg:row-start-1 lg:mx-auto lg:grid lg:w-full lg:max-w-7xl lg:grid-cols-2 lg:gap-x-8 lg:px-8">
				<div class="lg:pr-4">
					<div class="lg:max-w-lg">
						<p class="text-base/7 font-semibold text-red-600">Ship faster</p>
						<h1 class="mt-2 text-4xl font-semibold tracking-tight text-pretty text-gray-900 sm:text-5xl">
							Canadian Nutrition Facts Label Generator</h1>
						<p class="mt-6 text-xl/8 text-gray-700">
							Fill in the fields with accurate up to date nutrition information and then take a screenshot
							or hit export.
						</p>
					</div>
				</div>
			</div>
			<div
				class="-mt-12 -ml-12 p-12 lg:sticky lg:top-4 lg:col-start-2 lg:row-span-2 lg:row-start-1 lg:overflow-hidden">
				<Label :nutrition="nutrition" />
				<button @click="onDownload"
					class="rounded-md ml-18 md:ml-32 mt-4 bg-red-600 px-3.5 py-2.5 text-sm font-semibold text-white shadow-xs hover:bg-red-500 focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-red-600">Export
					Label</button>

			</div>
			<div
				class="lg:col-span-2 lg:col-start-1 lg:row-start-2 lg:mx-auto lg:grid lg:w-full lg:max-w-7xl lg:grid-cols-2 lg:gap-x-8 lg:px-8">
				<div class="lg:pr-4">
					<div class="max-w-xl text-base/7 text-gray-700 lg:max-w-lg">
						<Form @change="handleChange" :nutrition="nutrition" />
					</div>
					<p class="mt-6 text-lg text-gray-600">
						DISCLAIMER: This tool is made available in the hope that it will be useful, but WITHOUT ANY
						WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR
						PURPOSE.
						<a href="https://inspection.canada.ca/en/food-labels/labelling/industry/requirements-checklist"
							class="relative cursor-pointer rounded-md bg-white  text-red-600 focus-within:ring-2 focus-within:ring-red-600 focus-within:ring-offset-2 focus-within:outline-hidden hover:text-red-500">
							Review compliance documents
						</a>
					</p>
					<p class="mt-6 text-lg text-gray-600">
						Site by
						<a href="mailto:isaiahpaget@gmail.com"
							class="relative cursor-pointer rounded-md bg-white  text-red-600 focus-within:ring-2 focus-within:ring-red-600 focus-within:ring-offset-2 focus-within:outline-hidden hover:text-red-500">
							BYTEHEAD
						</a>
					</p>
				</div>
			</div>
		</div>
	</div>
</template>

<style scoped></style>
