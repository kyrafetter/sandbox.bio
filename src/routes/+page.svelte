<script>
import { Button, Icon } from "sveltestrap";
import { categories, explore, playgrounds } from "$stores/tutorials";
import Listings from "$components/Listings.svelte";
import TutorialList from "$src/components/TutorialList.svelte";
</script>

<svelte:head>
	<title>sandbox.bio</title>
</svelte:head>

<div class="container-fluid">
	<div class="row pb-0 pe-lg-0 bg-light align-items-center rounded-3 border shadow-lg">
		<div class="col-lg-6 p-3 p-lg-4 pt-lg-3">
			<h1 class="fw-bold" style="font-size: 30px">Interactive bioinformatics tutorials</h1>
			<p class="lead my-4">Learn bioinformatics from your browser. Everything runs in a sandbox, so you can experiment all you want.</p>
			<Button size="lg" color="primary" href="/tutorials">Get started <Icon name="arrow-right" /></Button>
			<Button size="lg" color="outline-primary" href="/about">Learn more</Button>
		</div>
		<div class="align-center col-lg-6 p-0 overflow-hidden shadow-lg d-none d-md-inline">
			<img class="rounded-lg-3" src="/screenshot-cli.png" alt="Screenshot of terminal and exercises" width="700" />
		</div>
	</div>
</div>

<h3 class="mt-5">Tutorials</h3>
<TutorialList categories={$categories} />
<hr class="mt-5" />

<h3 class="mt-5">Playgrounds</h3>
<Listings items={$playgrounds} />
<hr class="mt-5" />

<h3 class="mt-5">Explore</h3>
<Listings items={$explore} />

<style>
.bg-light {
	background-color: rgb(232, 240, 240) !important;
}
</style>
