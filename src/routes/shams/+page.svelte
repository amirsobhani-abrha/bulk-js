<svelte:head>
	<title>S&J | Shams</title>
	<meta name="description" content="An upcoming generative art project by S&J" />
</svelte:head>

<div class="container md:w-4/5 mx-auto my-10">
	<h1 class="text-2xl font-bold mx-10">Shams</h1>
	<h2 class="mb-10 mx-10">Points, colors and haloes</h2>

	<div class="grid mx-10 mb-20 gap-10">
		<a href="/shams/cover.png" target="_blank">
			<img class="shadow-2xl shadow-black mx-auto md:w-2/3" src="/shams/cover.png" alt="Sample output" />
		</a>
		<div>
			<h2 class="text-xl font-semibold mb-3 text-center">The concept</h2>
			<p class="mb-2">
				Shams (meaning sun in Arabic) aims to showcase the individual's striving for perfection.
				<br />
				<br />
				Each piece in this work of art is comprised of many small individual points, each with their own color, rotating
				around the center of the piece, as if they are revolving around their sun to try and form a number of perfect circles,
				while still maintaining their original color.
				<br />
				While sometimes they succeed in creating monotonous harmonic outputs, sometimes they don't, and instead result in
				snapshots of the work while they are still in movement; But what we want the viewer to ask of themselves is: Is trying
				to achieve perfection in this way truly what the individual wants? What rule of law establishes circles as the most
				perfect form? What is perfection after all, is it different than just trying to move forward and what this movement
				results in? Do perfection and individualism have to contradict each other?
				<br />
				<br />
				And lastly, which form do you - the viewer - see as more perfect, the completed harmonious circles, or the sparse,
				chaotic, unruly compositions of each individual's movement?
			</p>
		</div>
	</div>

	<div class="mx-10">
		<h2 class="text-xl font-semibold mb-0 text-center">The approach</h2>
		<p class="mb-3 text-center">Implemented in p5.js</p>
		<span>
			Each piece in Shams is created by defining a set of interconnected points on a route formed around the
			metaphorical sun - the center of the canvas - and then orbiting those points around the sun. Each moving point
			leaves its own color on the canvas wherever it moves, and multiple points moving over a single coordinate makes
			their respective colors blend into each other.
			<br />
		</span>
	</div>

	<h2 class="text-2xl font-bold mb-1 mx-10 mt-20 text-center">Sample gallery (WIP)</h2>
	<div class="grid md:grid-rows-3 md:grid-cols-4 grid-rows-6 grid-cols-2 mx-10 mt-5 gap-5">
		{#each [...Array(12).keys()] as i}
			<a href="/shams/sample{i + 1}.png" target="_blank">
				<img class="shadow-lg shadow-black" src="/shams/sample{i + 1}.png" alt="Sample output {i + 1}" />
			</a>
		{/each}
	</div>
</div>
