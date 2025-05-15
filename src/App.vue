<script setup lang="ts">
import { ref } from 'vue'
import * as htmlToImage from 'html-to-image';

const measurement = ref("")
const measurement_fr = ref("")
const measurement_metric = ref("")
const measurement_unit = ref("")
// const servings = ref("")

const calories = ref("")
const fats = ref("")
const fats_percent = ref("")
const saturated = ref("")
const saturated_percent = ref("")

const trans = ref("")

const carbs = ref("")

const fibre = ref("")
const fibre_percent = ref("")

const sugar = ref("")
const sugar_percent = ref("")

const protein = ref("")
const cholesterol = ref("")

const sodium = ref("")
const sodium_percent = ref("")

const potassium = ref("")
const potassium_percent = ref("")

const calcium = ref("")
const calcium_percent = ref("")

const iron = ref("")
const iron_percent = ref("")

const ingredients = ref("")
const ingredients_fr = ref("")
const may_contain = ref("")
const may_contain_fr = ref("")
const contains = ref("")
const contains_fr = ref("")

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
				<div id="nutritionlabel" class="w-[190pt] md:w-[285pt] p-4 shadow-xl rounded-2xl bg-white">
					<div
						class="border-[0.5pt] md:border-[0.75pt] p-[3pt] md:p-[4.5pt] leading-[10pt] md:leading-[15pt] text-[8pt] md:text-[12pt]">
						<h2 class="font-black text-[13pt] md:text-[19.5pt] leading-[14pt] md:leading-[21pt]">Nutrition
							Facts</h2>
						<h2 class="font-black text-[13pt] md:text-[19.5pt] leading-[14pt] md:leading-[21pt]">Valeur
							nutritive</h2>
						<p class="text-[9pt] md:text-[13.5pt] leading-[11pt] md:leading-[16.5pt]">Per {{ measurement }}
							({{ measurement_metric }} {{
								measurement_unit }})</p>
						<p class="text-[9pt] md:text-[13.5pt] leading-[11pt] md:leading-[16.5pt]">Pour {{ measurement_fr
							}} ({{ measurement_metric }} {{
								measurement_unit }})</p>
						<hr class="h-[1pt] md:h-[1.5pt] bg-black border-0 my-[1px]" />
						<div class="flex justify-between">
							<h3
								class="font-black underline underline-offset-3 mb-[2px] [text-decoration-thickness:3pt] md:[text-decoration-thickness:4.5pt] text-[10pt] md:text-[15pt] leading-[14.5pt] md:leading-[21.75pt]">
								Calories {{ calories }}</h3>
							<div>
								<p
									class="font-black text-[6pt] md:text-[9pt] leading-[7pt] md:leading-[10.5pt] text-end">
									% Daily Value<span
										class="font-normal text-[9pt] md:text-[13.5pt] [vertical-align:-1.5pt]">*</span>
								</p>
								<p
									class="font-black text-[6pt] md:text-[9pt] leading-[7pt] md:leading-[10.5pt] text-end">
									% valeur quotidienne<span
										class="font-normal text-[9pt] md:text-[13.5pt] [vertical-align:-1.5pt]">*</span>
								</p>
							</div>
						</div>
						<div class="flex justify-between items-center">
							<p class="font-black leading-[12pt] md:leading-[18pt]">Fat / Lipides <span
									class="font-normal">{{
										fats }}
									g</span></p>
							<p class="">{{ fats_percent }} %</p>
						</div>
						<div class="flex justify-between items-center relative">
							<p class="leading-[9pt] md:leading-[13.5pt] [text-indent:6pt] md:[text-indent:9pt]">
								Saturated / saturés <span class="font-normal">{{
									saturated }} g</span></p>
							<p class="absolute right-0 -bottom-1">{{ saturated_percent }} %</p>
						</div>
						<div class="flex justify-between items-center">
							<p class="leading-[9pt] md:leading-[13.5pt] [text-indent:6pt] md:[text-indent:9pt]"> + Trans
								/ trans <span class="font-normal">{{
									trans }} g</span></p>
						</div>
						<hr class="h-[0.5pt] md:h-[0.75pt] bg-black border-0 mt-[1pt]" />
						<div class="flex justify-between ">
							<p class="font-black leading-[12pt] md:leading-[18pt]">Carbohydrate / Glucides <span
									class="font-normal">{{
										carbs }} g</span></p>
						</div>
						<div class="flex justify-between items-center">
							<p class="leading-[9pt] md:leading-[13.5pt] [text-indent:6pt] md:[text-indent:9pt]">Fibre /
								Fibres <span class="font-normal">{{ fibre
								}} g</span></p>
							<p class="">{{ fibre_percent }} %</p>
						</div>
						<div class="flex justify-between items-center">
							<p class="leading-[9pt] md:leading-[13.5pt] [text-indent:6pt] md:[text-indent:9pt]">Sugars /
								Sucres <span class="font-normal">{{
									sugar }} g</span></p>
							<p class="">{{ sugar_percent }} %</p>
						</div>
						<hr class="h-[0.5pt] md:h-[0.75pt] bg-black border-0" />
						<div class="flex justify-between ">
							<p class="font-black leading-[12pt] md:leading-[18pt]">Protein / Protéines <span
									class="font-normal">{{
										protein }}
									g</span></p>
						</div>
						<hr class="h-[0.5pt] md:h-[0.75pt] bg-black border-0" />
						<div class="flex justify-between ">
							<p class="font-black leading-[12pt] md:leading-[18pt]">Cholesterol / Cholestérol <span
									class="font-normal">{{
										cholesterol }} mg</span></p>
						</div>
						<hr class="h-[0.5pt] md:h-[0.75pt] bg-black border-0" />
						<div class="flex justify-between items-center">
							<p class="font-black leading-[12pt] md:leading-[18pt]">Sodium <span class="font-normal">{{
									sodium }}
									mg</span></p>
							<p class="">{{ sodium_percent }} %</p>
						</div>
						<hr class="h-[2.5pt] md:h-[3.75pt] bg-black border-0" />
						<div class="flex justify-between items-center">
							<p class="leading-[12pt] md:leading-[18pt]">Potassium <span class="font-normal">{{ potassium
									}} mg</span>
							</p>
							<p class="">{{ potassium_percent }} %</p>
						</div>
						<hr class="h-[0.5pt] md:h-[0.75pt] bg-black border-0" />
						<div class="flex justify-between items-center">
							<p class="leading-[12pt] md:leading-[18pt]">Calcium <span class="font-normal">{{ calcium }}
									mg</span></p>
							<p class="">{{ calcium_percent }} %</p>
						</div>
						<hr class="h-[0.5pt] md:h-[0.75pt] bg-black border-0" />
						<div class="flex justify-between items-center">
							<p class="leading-[12pt] md:leading-[18pt]">Iron / Fer <span class="font-normal">{{ iron }}
									mg</span>
							</p>
							<p class="">{{ iron_percent }} %</p>
						</div>
						<hr class="h-[2.5pt] md:h-[3.75pt] bg-black border-0" />
						<div class="">
							<p class="text-[6.5pt] md:text-[9.75pt] leading-[13pt] md:leading-[19.5pt]"><span
									class="font-normal text-[9pt] md:text-[13.5pt] [vertical-align:-1.5pt]">*</span>5%
								or less is
								<strong>a
									little</strong>, 15% or more is <strong>a lot</strong>
							</p>
							<p class="text-[6.5pt] md:text-[9.75pt] leading-[2pt]"><span
									class="font-normal text-[9pt] md:text-[13.5pt] [vertical-align:-1.5pt]">*</span>5%
								ou moins c'est
								<strong>peu</strong>, 15% ou plus c'est <strong>beaucoup</strong>
							</p>
						</div>
					</div>
					<div class="text-[9pt] md:text-[13.5pt] leading-[9pt] md:leading-[13.5pt] text-center">
						<p>
							<strong>Ingredients: </strong>
							{{ ingredients }}
						</p>
						<p>
							<strong>Contains: </strong>

							{{ contains }}
						</p>
						<p>
							<strong>May contain: </strong>
							{{ may_contain }}

						</p>
						<p>
							<strong>Ingrédients: </strong>
							{{ ingredients_fr }}
						</p>
						<p>
							<strong>Contient: </strong>

							{{ contains_fr }}
						</p>
						<p>
							<strong>Peut contenir: </strong>
							{{ may_contain_fr }}
						</p>
					</div>
				</div>
				<button @click="onDownload"
					class="rounded-md ml-18 md:ml-32 mt-4 bg-red-600 px-3.5 py-2.5 text-sm font-semibold text-white shadow-xs hover:bg-red-500 focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-red-600">Export
					Label</button>

			</div>
			<div
				class="lg:col-span-2 lg:col-start-1 lg:row-start-2 lg:mx-auto lg:grid lg:w-full lg:max-w-7xl lg:grid-cols-2 lg:gap-x-8 lg:px-8">
				<div class="lg:pr-4">
					<div class="max-w-xl text-base/7 text-gray-700 lg:max-w-lg">
						<div class="mt-10 grid grid-cols-1 gap-x-6 gap-y-4 sm:grid-cols-6">

							<div class="col-span-full">
								<label for="measurement" class="block text-sm/6 font-medium text-gray-900">Household
									Measurement</label>
								<div class="mt-2">
									<input v-model="measurement" name="measurement" id="measurement" rows="3"
										placeholder="1/4 cup"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="col-span-full">
								<label for="measurement_fr" class="block text-sm/6 font-medium text-gray-900">Household
									Measurement
									French</label>
								<div class="mt-2">
									<input v-model="measurement_fr" name="measurement_fr" id="measurement_fr" rows="3"
										placeholder="1/4 tasse"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="sm:col-span-3">
								<label for="measurement_metric"
									class="block text-sm/6 font-medium text-gray-900">Measurement Metric</label>
								<div class="mt-2">
									<input v-model="measurement_metric" name="measurement_metric"
										id="measurement_metric" rows="3" placeholder="31"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="sm:col-span-3">
								<label for="unit" class="block text-sm/6 font-medium text-gray-900">Unit</label>
								<div class="mt-2 grid grid-cols-1">
									<select v-model="measurement_unit" id="unit" name="unit" autocomplete="unit-name"
										class="col-start-1 row-start-1 w-full appearance-none rounded-md bg-white py-1.5 pr-8 pl-3 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6">
										<option class="text-gray-400" value="">Select a unit</option>
										<option value="g">Grams</option>
										<option value="ml">Mililitres</option>
									</select>

								</div>
							</div>

							<!-- <div class="col-span-full"> -->
							<!-- 	<label for="servings" class="block text-sm/6 font-medium text-gray-900">Servings</label> -->
							<!-- 	<div class="mt-2"> -->
							<!-- 		<input v-model="servings" name="servings" id="servings" rows="3" placeholder="6" -->
							<!-- 			class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" /> -->
							<!-- 	</div> -->
							<!-- </div> -->
							<div class="col-span-full">
								<label for="calories" class="block text-sm/6 font-medium text-gray-900">Calories</label>
								<div class="mt-2">
									<input v-model="calories" name="calories" id="calories" rows="3" placeholder="110"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="sm:col-span-3">
								<label for="fats" class="block text-sm/6 font-medium text-gray-900">Fats</label>
								<div class="mt-2">
									<input v-model="fats" name="fats" id="fats" rows="3" placeholder="2"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="sm:col-span-3">
								<label for="fats_percent" class="block text-sm/6 font-medium text-gray-900">Fats
									%</label>
								<div class="mt-2">
									<input v-model="fats_percent" name="fats_percent" id="fats_percent" rows="3"
										placeholder="3"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="sm:col-span-2">
								<label for="saturated"
									class="block text-sm/6 font-medium text-gray-900">Saturated</label>
								<div class="mt-2">
									<input v-model="saturated" name="saturated" id="saturated" rows="3" placeholder="1"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="sm:col-span-2">
								<label for="trans" class="block text-sm/6 font-medium text-gray-900">Trans</label>
								<div class="mt-2">
									<input v-model="trans" name="trans" id="trans" rows="3" placeholder="0"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="sm:col-span-2">
								<label for="saturated_percent"
									class="block text-sm/6 font-medium text-gray-900">Saturated +
									Trans %</label>
								<div class="mt-2">
									<input v-model="saturated_percent" name="saturated_percent" id="saturated_percent"
										rows="3" placeholder="5"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="col-span-full">
								<label for="carbs"
									class="block text-sm/6 font-medium text-gray-900">Carbohydrates</label>
								<div class="mt-2">
									<input v-model="carbs" name="carbs" id="carbs" rows="3" placeholder="17"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="sm:col-span-3">
								<label for="fibre" class="block text-sm/6 font-medium text-gray-900">Fibre</label>
								<div class="mt-2">
									<input v-model="fibre" name="fibre" id="fibre" rows="3" placeholder="2"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="sm:col-span-3">
								<label for="fibre_percent" class="block text-sm/6 font-medium text-gray-900">Fibre
									%</label>
								<div class="mt-2">
									<input v-model="fibre_percent" name="fibre_percent" id="fibre_percent" rows="3"
										placeholder="7"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="sm:col-span-3">
								<label for="sugar" class="block text-sm/6 font-medium text-gray-900">Sugar</label>
								<div class="mt-2">
									<input v-model="sugar" name="sugar" id="sugar" rows="3" placeholder="6"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="sm:col-span-3">
								<label for="sugar_percent" class="block text-sm/6 font-medium text-gray-900">Sugar
									%</label>
								<div class="mt-2">
									<input v-model="sugar_percent" name="sugar_percent" id="sugar_percent" rows="3"
										placeholder="6"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="col-span-full">
								<label for="protein" class="block text-sm/6 font-medium text-gray-900">Protein</label>
								<div class="mt-2">
									<input v-model="protein" name="protein" id="protein" rows="3" placeholder="8"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="col-span-full">
								<label for="cholesterol"
									class="block text-sm/6 font-medium text-gray-900">Cholesterol</label>
								<div class="mt-2">
									<input v-model="cholesterol" name="cholesterol" id="cholesterol" rows="3"
										placeholder="5"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="sm:col-span-3">
								<label for="sodium" class="block text-sm/6 font-medium text-gray-900">Sodium</label>
								<div class="mt-2">
									<input v-model="sodium" name="sodium" id="sodium" rows="3" placeholder="210"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="sm:col-span-3">
								<label for="sodium_percent" class="block text-sm/6 font-medium text-gray-900">Sodium
									%</label>
								<div class="mt-2">
									<input v-model="sodium_percent" name="sodium_percent" id="sodium_percent" rows="3"
										placeholder="9"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="sm:col-span-3">
								<label for="potassium"
									class="block text-sm/6 font-medium text-gray-900">Potassium</label>
								<div class="mt-2">
									<input v-model="potassium" name="potassium" id="potassium" rows="3"
										placeholder="100"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="sm:col-span-3">
								<label for="potassium_percent"
									class="block text-sm/6 font-medium text-gray-900">Potassium
									%</label>
								<div class="mt-2">
									<input v-model="potassium_percent" name="potassium_percent" id="potassium_percent"
										rows="3" placeholder="2"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="sm:col-span-3">
								<label for="calcium" class="block text-sm/6 font-medium text-gray-900">Calcium</label>
								<div class="mt-2">
									<input v-model="calcium" name="calcium" id="calcium" rows="3" placeholder="125"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="sm:col-span-3">
								<label for="calcium_percent" class="block text-sm/6 font-medium text-gray-900">Calcium
									%</label>
								<div class="mt-2">
									<input v-model="calcium_percent" name="calcium_percent" id="calcium_percent"
										rows="3" placeholder="10"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="sm:col-span-3">
								<label for="iron" class="block text-sm/6 font-medium text-gray-900">Iron</label>
								<div class="mt-2">
									<input v-model="iron" name="iron" id="iron" rows="3" placeholder="1"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="sm:col-span-3">
								<label for="iron_percent" class="block text-sm/6 font-medium text-gray-900">Iron
									%</label>
								<div class="mt-2">
									<input v-model="iron_percent" name="iron_percent" id="iron_percent" rows="3"
										placeholder="6"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="col-span-full">
								<label for="ingredients"
									class="block text-sm/6 font-medium text-gray-900">Ingredients</label>
								<div class="mt-2">
									<textarea v-model="ingredients" name="ingredients" id="ingredients" rows="3"
										placeholder="Whole grain wheat flour, Sugars, Whey Protein"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="col-span-full">
								<label for="contains" class="block text-sm/6 font-medium text-gray-900">Contains</label>
								<div class="mt-2">
									<textarea v-model="contains" name="contains" id="contains" rows="3"
										placeholder="Milk, Oats, Soy, Wheat"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="col-span-full">
								<label for="may_contain" class="block text-sm/6 font-medium text-gray-900">May
									Contain</label>
								<div class="mt-2">
									<textarea v-model="may_contain" name="contains" id="contains" rows="3"
										placeholder="Egg, Tree nuts"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="col-span-full">
								<label for="ingredients_fr"
									class="block text-sm/6 font-medium text-gray-900">Ingredients
									French</label>
								<div class="mt-2">
									<textarea v-model="ingredients_fr" name="ingredients_fr" id="ingredients_fr"
										rows="3" placeholder="wheat flour, sugar, eggs"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="col-span-full">
								<label for="contains_fr" class="block text-sm/6 font-medium text-gray-900">Contains
									French</label>
								<div class="mt-2">
									<textarea v-model="contains_fr" name="contains_fr" id="contains_fr" rows="3"
										placeholder="wheat flour, sugar, eggs"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
							<div class="col-span-full">
								<label for="may_contain_fr" class="block text-sm/6 font-medium text-gray-900">May
									Contain French</label>
								<div class="mt-2">
									<textarea v-model="may_contain_fr" name="may_contain_fr" id="may_contain_fr"
										rows="3" placeholder="wheat flour, sugar, eggs"
										class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
								</div>
							</div>
						</div>
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
