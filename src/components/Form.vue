<script setup lang="ts">
import { watch } from 'vue';
import type { Nutrition } from '../types';

const props = defineProps<{ nutrition: Nutrition }>()
const emit = defineEmits<{ change: [Nutrition] }>()
watch(props.nutrition, () => {
	emit('change', props.nutrition)
})

</script>
<template>
	<form class="mt-10 grid grid-cols-1 gap-x-6 gap-y-4 sm:grid-cols-6">

		<div class="col-span-full">
			<label for="measurement" class="block text-sm/6 font-medium text-gray-900">Household
				Measurement</label>
			<div class="mt-2">
				<input v-model="nutrition.measurement" name="measurement" id="measurement" rows="3"
					placeholder="1/4 cup"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="col-span-full">
			<label for="measurement_fr" class="block text-sm/6 font-medium text-gray-900">Household
				Measurement
				French</label>
			<div class="mt-2">
				<input v-model="nutrition.measurement_fr" name="measurement_fr" id="measurement_fr" rows="3"
					placeholder="1/4 tasse"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="sm:col-span-3">
			<label for="measurement_metric" class="block text-sm/6 font-medium text-gray-900">Measurement
				Metric</label>
			<div class="mt-2">
				<input v-model="nutrition.measurement_metric" name="measurement_metric" id="measurement_metric" rows="3"
					placeholder="31"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="sm:col-span-3">
			<label for="unit" class="block text-sm/6 font-medium text-gray-900">Unit</label>
			<div class="mt-2 grid grid-cols-1">
				<select v-model="nutrition.measurement_unit" id="unit" name="unit" autocomplete="unit-name"
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
				<input v-model="nutrition.calories" name="calories" id="calories" rows="3" placeholder="110"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="sm:col-span-3">
			<label for="fats" class="block text-sm/6 font-medium text-gray-900">Fats</label>
			<div class="mt-2">
				<input v-model="nutrition.fats" name="fats" id="fats" rows="3" placeholder="2"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="sm:col-span-3">
			<label for="fats_percent" class="block text-sm/6 font-medium text-gray-900">Fats
				%</label>
			<div class="mt-2">
				<input v-model="nutrition.fats_percent" name="fats_percent" id="fats_percent" rows="3" placeholder="3"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="sm:col-span-2">
			<label for="saturated" class="block text-sm/6 font-medium text-gray-900">Saturated</label>
			<div class="mt-2">
				<input v-model="nutrition.saturated" name="saturated" id="saturated" rows="3" placeholder="1"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="sm:col-span-2">
			<label for="trans" class="block text-sm/6 font-medium text-gray-900">Trans</label>
			<div class="mt-2">
				<input v-model="nutrition.trans" name="trans" id="trans" rows="3" placeholder="0"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="sm:col-span-2">
			<label for="saturated_percent" class="block text-sm/6 font-medium text-gray-900">Saturated +
				Trans %</label>
			<div class="mt-2">
				<input v-model="nutrition.saturated_percent" name="saturated_percent" id="saturated_percent" rows="3"
					placeholder="5"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="col-span-full">
			<label for="carbs" class="block text-sm/6 font-medium text-gray-900">Carbohydrates</label>
			<div class="mt-2">
				<input v-model="nutrition.carbs" name="carbs" id="carbs" rows="3" placeholder="17"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="sm:col-span-3">
			<label for="fibre" class="block text-sm/6 font-medium text-gray-900">Fibre</label>
			<div class="mt-2">
				<input v-model="nutrition.fibre" name="fibre" id="fibre" rows="3" placeholder="2"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="sm:col-span-3">
			<label for="fibre_percent" class="block text-sm/6 font-medium text-gray-900">Fibre
				%</label>
			<div class="mt-2">
				<input v-model="nutrition.fibre_percent" name="fibre_percent" id="fibre_percent" rows="3"
					placeholder="7"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="sm:col-span-3">
			<label for="sugar" class="block text-sm/6 font-medium text-gray-900">Sugar</label>
			<div class="mt-2">
				<input v-model="nutrition.sugar" name="sugar" id="sugar" rows="3" placeholder="6"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="sm:col-span-3">
			<label for="sugar_percent" class="block text-sm/6 font-medium text-gray-900">Sugar
				%</label>
			<div class="mt-2">
				<input v-model="nutrition.sugar_percent" name="sugar_percent" id="sugar_percent" rows="3"
					placeholder="6"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="col-span-full">
			<label for="protein" class="block text-sm/6 font-medium text-gray-900">Protein</label>
			<div class="mt-2">
				<input v-model="nutrition.protein" name="protein" id="protein" rows="3" placeholder="8"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="col-span-full">
			<label for="cholesterol" class="block text-sm/6 font-medium text-gray-900">Cholesterol</label>
			<div class="mt-2">
				<input v-model="nutrition.cholesterol" name="cholesterol" id="cholesterol" rows="3" placeholder="5"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="sm:col-span-3">
			<label for="sodium" class="block text-sm/6 font-medium text-gray-900">Sodium</label>
			<div class="mt-2">
				<input v-model="nutrition.sodium" name="sodium" id="sodium" rows="3" placeholder="210"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="sm:col-span-3">
			<label for="sodium_percent" class="block text-sm/6 font-medium text-gray-900">Sodium
				%</label>
			<div class="mt-2">
				<input v-model="nutrition.sodium_percent" name="sodium_percent" id="sodium_percent" rows="3"
					placeholder="9"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="sm:col-span-3">
			<label for="potassium" class="block text-sm/6 font-medium text-gray-900">Potassium</label>
			<div class="mt-2">
				<input v-model="nutrition.potassium" name="potassium" id="potassium" rows="3" placeholder="100"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="sm:col-span-3">
			<label for="potassium_percent" class="block text-sm/6 font-medium text-gray-900">Potassium
				%</label>
			<div class="mt-2">
				<input v-model="nutrition.potassium_percent" name="potassium_percent" id="potassium_percent" rows="3"
					placeholder="2"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="sm:col-span-3">
			<label for="calcium" class="block text-sm/6 font-medium text-gray-900">Calcium</label>
			<div class="mt-2">
				<input v-model="nutrition.calcium" name="calcium" id="calcium" rows="3" placeholder="125"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="sm:col-span-3">
			<label for="calcium_percent" class="block text-sm/6 font-medium text-gray-900">Calcium
				%</label>
			<div class="mt-2">
				<input v-model="nutrition.calcium_percent" name="calcium_percent" id="calcium_percent" rows="3"
					placeholder="10"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="sm:col-span-3">
			<label for="iron" class="block text-sm/6 font-medium text-gray-900">Iron</label>
			<div class="mt-2">
				<input v-model="nutrition.iron" name="iron" id="iron" rows="3" placeholder="1"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="sm:col-span-3">
			<label for="iron_percent" class="block text-sm/6 font-medium text-gray-900">Iron
				%</label>
			<div class="mt-2">
				<input v-model="nutrition.iron_percent" name="iron_percent" id="iron_percent" rows="3" placeholder="6"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="col-span-full">
			<label for="ingredients" class="block text-sm/6 font-medium text-gray-900">Ingredients</label>
			<div class="mt-2">
				<textarea v-model="nutrition.ingredients" name="ingredients" id="ingredients" rows="3"
					placeholder="Whole grain wheat flour, Sugars, Whey Protein"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="col-span-full">
			<label for="contains" class="block text-sm/6 font-medium text-gray-900">Contains</label>
			<div class="mt-2">
				<textarea v-model="nutrition.contains" name="contains" id="contains" rows="3"
					placeholder="Milk, Oats, Soy, Wheat"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="col-span-full">
			<label for="may_contain" class="block text-sm/6 font-medium text-gray-900">May
				Contain</label>
			<div class="mt-2">
				<textarea v-model="nutrition.may_contain" name="contains" id="contains" rows="3"
					placeholder="Egg, Tree nuts"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="col-span-full">
			<label for="ingredients_fr" class="block text-sm/6 font-medium text-gray-900">Ingredients
				French</label>
			<div class="mt-2">
				<textarea v-model="nutrition.ingredients_fr" name="ingredients_fr" id="ingredients_fr" rows="3"
					placeholder="wheat flour, sugar, eggs"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="col-span-full">
			<label for="contains_fr" class="block text-sm/6 font-medium text-gray-900">Contains
				French</label>
			<div class="mt-2">
				<textarea v-model="nutrition.contains_fr" name="contains_fr" id="contains_fr" rows="3"
					placeholder="wheat flour, sugar, eggs"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
		<div class="col-span-full">
			<label for="may_contain_fr" class="block text-sm/6 font-medium text-gray-900">May
				Contain French</label>
			<div class="mt-2">
				<textarea v-model="nutrition.may_contain_fr" name="may_contain_fr" id="may_contain_fr" rows="3"
					placeholder="wheat flour, sugar, eggs"
					class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
			</div>
		</div>
	</form>
</template>
