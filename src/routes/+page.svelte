<script>
	import Newsletter from '../components/Newsletter.svelte';
	import FeatureCard from '../components/FeatureCard.svelte';
	import LatestPosts from '../components/LatestPosts.svelte';
	import NavLink from '../components/NavLink.svelte';
	import {
		SITE_URL,
		REPO_URL,
		SITE_TITLE,
		SITE_DESCRIPTION,
		DEFAULT_OG_IMAGE,
		MY_TWITTER_HANDLE
	} from '$lib/siteConfig';

	/** @type {import('./$types').PageData} */
	export let data;
	// technically this is a slighlty different type because doesnt have 'content' but we'll let it slide
	/** @type {import('$lib/types').ContentItem[]} */
	$: items = data.items;
</script>

<svelte:head>
	<title>{SITE_TITLE}</title>
	<link rel="canonical" href={SITE_URL} />
	<link rel="alternate" type="application/rss+xml" href={SITE_URL + '/rss.xml'} />
	<meta property="og:url" content={SITE_URL} />
	<meta property="og:type" content="article" />
	<meta property="og:title" content={SITE_TITLE} />
	<meta name="Description" content={SITE_DESCRIPTION} />
	<meta property="og:description" content={SITE_DESCRIPTION} />
	<meta property="og:image" content={DEFAULT_OG_IMAGE} />
	<meta name="twitter:card" content="summary" />
	<meta name="twitter:creator" content={'@' + MY_TWITTER_HANDLE} />
	<meta name="twitter:title" content={SITE_TITLE} />
	<meta name="twitter:description" content={SITE_DESCRIPTION} />
	<meta name="twitter:image" content={DEFAULT_OG_IMAGE} />
</svelte:head>

<div
	class="flex flex-col items-start justify-center max-w-5xl px-4 pb-16 mx-auto border-gray-200 dark:border-gray-700 sm:px-8"
>
	<div class="flex flex-col-reverse items-start sm:flex-row">
		<div class="flex flex-col pr-8">
			<h1 class="mb-6 text-3xl tracking-tight text-gray-600  dark:text-white md:text-5xl">{SITE_TITLE}</h1>
			<p class="mb-6 text-gray-500 dark:text-gray-300 text-4xl md:text-4xl">Independent Researcher
		</div>

		<!--<div class="flex flex-col pr-8">
			<h1 class="mb-3 text-3xl font-bold tracking-tight text-black dark:text-white md:text-5xl">
				This is

				<span
					class="relative inline-block ml-2 before:absolute before:-inset-1 before:block before:-skew-y-3 before:bg-red-500"
				>
					<span class="relative text-yellow-400 skew-y-3">{SITE_TITLE}</span>
				</span>
				!
			</h1>
			<h2 class="mb-4 text-gray-700 dark:text-gray-200">
				My bespoke Github-powered personal site. Total overkill but screw it.
			</h2>
			<p class="mb-16 text-gray-600 dark:text-gray-400">
				<a href={REPO_URL}>View source and feature list here!</a>
			</p>
		</div>-->
		<!-- <div
				class="w-[80px] h-[80px] rounded-full sm:w-[176px] sm:h-[136px] relative mb-8 sm:mb-0 mr-auto bg-cyan-300 bg-opacity-25"
			/> -->
	</div>

	<section class="w-full mb-16">
		<h3 class="mb-6 text-2xl tracking-tight text-gray-400 dark:text-gray-200 md:text-3xl">
			Hi, thanks for stopping by. I'm busy at the moment tinkering on things behind the scenes. But if you find some of prompts below appealing, I'd love to chat.
		</h3>
		<div class="flex flex-col gap-6 md:flex-row">
			<FeatureCard title="Apple Vision Pro is cool, but do you find Spatial Computing to feel a little impoverished?" href="/an-early-manifesto-for-spatial-computing" caption="I'm working with Sloan to expand the vocabulary of extended reality design patterns. In others, shared ontologies." stringData="XR, UX, EGO" />
			<FeatureCard
				title="The Enterprise Strikes Back"
				href="/enterprise Strikes Back"
				caption="The silent killer of productivity in the enterprise is documentation. Folders and files too industrial. Hyperlinks are overextended. Even ChatGPT will not be able to quell the information epidemic."
				stringData="LLMs, TfT, Doc Ops"
			/>
			<FeatureCard title="Scrollspace: Experiments in Analog Spatial Computing" href="/tablescroll-an-experiment-in-analog-spatial-computing" caption="A 100ft experiment to imagine what it would be like to think on *paper*. A lot of spilled ink." stringData="Paper, OCR, Analog" />
		</div>
	</section>
	<!-- <section class="w-full mb-16">
		<pre>{JSON.stringify(speaking, null, 2)}</pre>
	</section> -->
	
	<!--<LatestPosts {items} />-->
	<!--<Newsletter />-->
</div>
