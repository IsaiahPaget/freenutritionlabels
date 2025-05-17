<script setup lang="ts">
import type { Nutrition } from '../types';

defineProps<{ nutrition: Nutrition }>()


</script>
<template>
	<div id="nutritionlabel" class="w-[190pt] md:w-[285pt] p-4 shadow-xl rounded-2xl bg-white">
		<div
			class="border-[0.5pt] md:border-[0.75pt] p-[3pt] md:p-[4.5pt] leading-[10pt] md:leading-[15pt] text-[8pt] md:text-[12pt]">
			<h2 class="font-black text-[13pt] md:text-[19.5pt] leading-[14pt] md:leading-[21pt]">Nutrition
				Facts</h2>
			<h2 class="font-black text-[13pt] md:text-[19.5pt] leading-[14pt] md:leading-[21pt]">Valeur
				nutritive</h2>
			<p class="text-[9pt] md:text-[13.5pt] leading-[11pt] md:leading-[16.5pt]">Per {{ nutrition.measurement }}
				({{ nutrition.measurement_metric }} {{
					nutrition.measurement_unit }})</p>
			<p class="text-[9pt] md:text-[13.5pt] leading-[11pt] md:leading-[16.5pt]">Pour {{ nutrition.measurement_fr
			}} ({{ nutrition.measurement_metric }} {{
					nutrition.measurement_unit }})</p>
			<hr class="h-[1pt] md:h-[1.5pt] bg-black border-0 my-[1px] md:my-[1.5px]" />
			<div class="flex justify-between">
				<h3
					class="font-black underline underline-offset-3 mb-[2px] md:mb-[3px] [text-decoration-thickness:3pt] md:[text-decoration-thickness:4.5pt] text-[10pt] md:text-[15pt] leading-[14.5pt] md:leading-[21.75pt]">
					Calories {{ nutrition.calories }}</h3>
				<div>
					<p class="font-black text-[6pt] md:text-[9pt] leading-[7pt] md:leading-[10.5pt] text-end">
						% Daily Value<span
							class="font-normal text-[9pt] md:text-[13.5pt] [vertical-align:-1.5pt] md:[vertical-align:-2.25pt]">*</span>
					</p>
					<p class="font-black text-[6pt] md:text-[9pt] leading-[7pt] md:leading-[10.5pt] text-end">
						% valeur quotidienne<span
							class="font-normal text-[9pt] md:text-[13.5pt] [vertical-align:-1.5pt] md:[vertical-align:-2.25pt]">*</span>
					</p>
				</div>
			</div>
			<div class="flex justify-between items-center">
				<p class="font-black leading-[12pt] md:leading-[18pt]">Fat / Lipides <span class="font-normal">{{
					nutrition.fats }}
						g</span></p>
				<p class="">{{ nutrition.fats_percent }} %</p>
			</div>
			<div class="flex justify-between items-center relative">
				<p class="leading-[9pt] md:leading-[13.5pt] [text-indent:6pt] md:[text-indent:9pt]">
					Saturated / saturés <span class="font-normal">{{
						nutrition.saturated }} g</span></p>
				<p class="absolute right-0 -bottom-1.5 md:-bottom-2.5">{{ nutrition.saturated_percent }} %</p>
			</div>
			<div class="flex justify-between items-center">
				<p class="leading-[9pt] md:leading-[13.5pt] [text-indent:6pt] md:[text-indent:9pt]"> + Trans
					/ trans <span class="font-normal">{{
						nutrition.trans }} g</span></p>
			</div>
			<hr class="h-[0.5pt] md:h-[0.75pt] bg-black border-0 mt-[1pt]" />
			<div class="flex justify-between ">
				<p class="font-black leading-[12pt] md:leading-[18pt]">Carbohydrate / Glucides <span
						class="font-normal">{{
							nutrition.carbs }} g</span></p>
			</div>
			<div class="flex justify-between items-center">
				<p class="leading-[9pt] md:leading-[13.5pt] [text-indent:6pt] md:[text-indent:9pt]">Fibre /
					Fibres <span class="font-normal">{{ nutrition.fibre
					}} g</span></p>
				<p class="">{{ nutrition.fibre_percent }} %</p>
			</div>
			<div class="flex justify-between items-center">
				<p class="leading-[9pt] md:leading-[13.5pt] [text-indent:6pt] md:[text-indent:9pt]">Sugars /
					Sucres <span class="font-normal">{{
						nutrition.sugar }} g</span></p>
				<p class="">{{ nutrition.sugar_percent }} %</p>
			</div>
			<hr class="h-[0.5pt] md:h-[0.75pt] bg-black border-0" />
			<div class="flex justify-between ">
				<p class="font-black leading-[12pt] md:leading-[18pt]">Protein / Protéines <span class="font-normal">{{
					nutrition.protein }}
						g</span></p>
			</div>
			<hr class="h-[0.5pt] md:h-[0.75pt] bg-black border-0" />
			<div class="flex justify-between ">
				<p class="font-black leading-[12pt] md:leading-[18pt]">Cholesterol / Cholestérol <span
						class="font-normal">{{
							nutrition.cholesterol }} mg</span></p>
			</div>
			<hr class="h-[0.5pt] md:h-[0.75pt] bg-black border-0" />
			<div class="flex justify-between items-center">
				<p class="font-black leading-[12pt] md:leading-[18pt]">Sodium <span class="font-normal">{{
					nutrition.sodium }}
						mg</span></p>
				<p class="">{{ nutrition.sodium_percent }} %</p>
			</div>
			<hr class="h-[2.5pt] md:h-[3.75pt] bg-black border-0" />
			<div class="flex justify-between items-center">
				<p class="leading-[12pt] md:leading-[18pt]">Potassium <span class="font-normal">{{ nutrition.potassium
						}} mg</span>
				</p>
				<p class="">{{ nutrition.potassium_percent }} %</p>
			</div>
			<hr class="h-[0.5pt] md:h-[0.75pt] bg-black border-0" />
			<div class="flex justify-between items-center">
				<p class="leading-[12pt] md:leading-[18pt]">Calcium <span class="font-normal">{{ nutrition.calcium }}
						mg</span></p>
				<p class="">{{ nutrition.calcium_percent }} %</p>
			</div>
			<hr class="h-[0.5pt] md:h-[0.75pt] bg-black border-0" />
			<div class="flex justify-between items-center">
				<p class="leading-[12pt] md:leading-[18pt]">Iron / Fer <span class="font-normal">{{ nutrition.iron }}
						mg</span>
				</p>
				<p class="">{{ nutrition.iron_percent }} %</p>
			</div>
			<hr class="h-[2.5pt] md:h-[3.75pt] bg-black border-0" />
			<div class="">
				<p class="text-[6.5pt] md:text-[9.75pt] leading-[13pt] md:leading-[19.5pt]"><span
						class="font-normal text-[9pt] md:text-[13.5pt] [vertical-align:-1.5pt] md:[vertical-align:-2.25pt]">*</span>5%
					or less is
					<strong>a
						little</strong>, 15% or more is <strong>a lot</strong>
				</p>
				<p class="text-[6.5pt] md:text-[9.75pt] leading-[2pt] md:leading-[3pt]"><span
						class="font-normal text-[9pt] md:text-[13.5pt] [vertical-align:-1.5pt] md:[vertical-align:-2.25pt]">*</span>5%
					ou moins c'est
					<strong>peu</strong>, 15% ou plus c'est <strong>beaucoup</strong>
				</p>
			</div>
		</div>
		<div class="text-[9pt] md:text-[13.5pt] leading-[9pt] md:leading-[13.5pt] text-center">
			<p>
				<strong>Ingredients: </strong>
				{{ nutrition.ingredients }}
			</p>
			<p>
				<strong>Contains: </strong>

				{{ nutrition.contains }}
			</p>
			<p>
				<strong>May contain: </strong>
				{{ nutrition.may_contain }}

			</p>
			<p>
				<strong>Ingrédients: </strong>
				{{ nutrition.ingredients_fr }}
			</p>
			<p>
				<strong>Contient: </strong>

				{{ nutrition.contains_fr }}
			</p>
			<p>
				<strong>Peut contenir: </strong>
				{{ nutrition.may_contain_fr }}
			</p>
		</div>
	</div>
</template>
