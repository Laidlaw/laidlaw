<script>
	export let title = 'Untitled post';
	export let href = '#';
	export let caption = 'I forgot to write something here';
	/** @type {string} */
	export let stringData; // we intentionally force this prop to be a string, not children, because dont want to allow arbitrary display of components for such a small contained component. feel free to refactor this if you need to
</script>

<a class="w-full transform rounded-xl p-1 transition-all hover:scale-[1.01] md:w-1/3"
	{href}
	><div class="flex h-full flex-col justify-between rounded-lg bg-white p-4 dark:bg-gray-900">
		<div class="flex flex-col justify-between md:flex-row">
			<h3 class="mb-6 w-full text-xl font-medium tracking-tight text-gray-900 dark:text-gray-100 sm:mb-10 md:text-xl">
				{title}
			</h3>
		</div>
		<p class="flex text-slate-500 dark:text-gray-200">
			{caption}
		</p>
		<div class="capsize flex items-center text-gray-800 dark:text-gray-200">
			{stringData}
		</div>
	</div></a>
