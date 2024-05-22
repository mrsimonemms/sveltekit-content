<script lang="ts">
	import type { PageData } from './$types';
	import Opengraph from '$lib/components/opengraph.svelte';

	export let data: PageData;
</script>

<Opengraph
	title={data.content.content.title}
	description={data.content.content.excerpt}
	image="/img/{data.content.content.slug}/{data.content.content.image ??
		'banner.jpg'}"
	type="article"
	keywords={data.content.content.tags}
	useTwitterSummaryImage={data.content.content.useTwitterSummaryImage}
/>

<svelte:component this={data.content.Component} {data} />
