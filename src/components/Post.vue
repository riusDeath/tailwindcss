<template>
	<div class="bg-white dark:bg-slate-900 px-6 py-8 ring-1 ring-slate-900/5">
		<h2 class="text-slate-900 dark:text-white mt-5 text-3xl font-medium tracking-tight">Writes Upside-Down</h2>
		<p class="text-slate-500 dark:text-slate-400 mt-2 text-sm">
			The Zero Gravity Pen can be used to write in any orientation, including upside-down. It even works in outer space.
		</p>
	</div>
</template>

<style scoped>
input:checked ~ .dot {
  transform: translateX(100%);
  background-color: #48bb78;
}
</style>