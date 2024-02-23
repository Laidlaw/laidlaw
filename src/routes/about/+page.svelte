<script>
    import { SITE_TITLE, POST_CATEGORIES } from '$lib/siteConfig';
    import About from './about.svx';
</script>

<svelte:head>
	<title>About {SITE_TITLE}</title>
	<meta name="description" content={`About ${SITE_TITLE}`} />
</svelte:head>
<section class="mx-auto flex max-w-5xl flex-col items-start justify-center px-4 sm:px-8">
	
    <div class="flex flex-col-reverse items-start sm:flex-row">
        <div class="flex flex-col pr-8">
            <About/>
        </div>
    </div>

</section>