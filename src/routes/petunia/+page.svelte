<script>
	let step = 1;
</script>

<svelte:head>
	<title>S&J | Petunia</title>
	<meta name="description" content="Petunia - a generative art project by S&J" />
</svelte:head>

<div class="container md:w-4/5 mx-auto my-10">
	<h1 class="text-2xl font-bold mx-10">Petunia</h1>
	<h2 class="mb-10 mx-10">An imitation of an imitation</h2>

	<div class="grid mx-10 mb-20 gap-10">
		<a href="/petunia/cover.png" target="_blank">
			<img class="shadow-2xl shadow-black mx-auto md:w-2/3" src="/petunia/cover.png" alt="Sample output" />
		</a>
		<div>
			<h2 class="text-xl font-semibold mb-3 text-center">The concept</h2>
			<p class="mb-2">Beauty from roughness.</p>
			<p class="mb-2">
				Petunia is inspired by the chain pull technique of painting. We tried to present a simulation of that technique,
				which itself tries to imitate nature by making use of large beaded chains and acrylic colors. Therefore, what we
				created might be considered an imitation of an imitation.
			</p>
			<p>
				There is a subtle contradiction in using metal chains in order to depict delicate flowers; Entirely man-made and
				lifeless objects being used to simulate vibrant forms of life and nature. It brings to mind the inevitable,
				unwavering resolve of nature to persevere and flourish despite the harshest circumstances.
			</p>
		</div>
	</div>

	<div class="mx-10">
		<h2 class="text-xl font-semibold mb-0 text-center">The approach</h2>
		<p class="mb-3 text-center">Implemented entirely in p5.js</p>

		<div class="flex md:flex-row flex-col-reverse my-10 gap-5">
			<a class="md:w-1/2" href="/petunia/step{step}.{step === 3 ? 'gif' : 'png'}" target="_blank">
				<img
					class="shadow-2xl shadow-black"
					src="/petunia/step{step}.{step === 3 ? 'gif' : 'png'}"
					alt="An output utilizing both the CPU and the GPU"
				/>
			</a>
			<span class="md:w-1/2 flex flex-col justify-around">
				<span
					class={step === 1 ? 'font-bold' : ''}
					role="button"
					tabindex="0"
					on:click={() => (step = 1)}
					on:keydown={(e) => {
						if (e.key === 'Enter') step = 1;
					}}
				>
					<h3 class="text-lg mb-1">1. Generate geometric composition</h3>
					<p class="mb-3">
						The overall composition of the output is randomly picked from several predesigned compositions and the
						available perimeter of flowers for each layer is incrementally built starting from the innermost layer.
					</p>
				</span>
				<span
					class={step === 2 ? 'font-bold' : ''}
					role="button"
					tabindex="0"
					on:click={() => (step = 2)}
					on:keydown={(e) => {
						if (e.key === 'Enter') step = 2;
					}}
				>
					<h3 class="text-lg mb-1">2. Create and place the chains</h3>
					<p class="mb-3">
						The chains are placed on the entire available perimeter for each layer. Each chain is an ellipse with its
						points displaced using the Perlin noise algorithm.
					</p>
				</span>
				<span
					class={step === 3 ? 'font-bold' : ''}
					role="button"
					tabindex="0"
					on:click={() => (step = 3)}
					on:keydown={(e) => {
						if (e.key === 'Enter') step = 3;
					}}
				>
					<h3 class="text-lg mb-1">3. Pulling the chains</h3>
					<p>
						Each chain's first bead is pulled towards a specific focal point, with the other beads following the trace
						of the pulled bead while calculating their direction and velocity using mathematical formulas, simulating a
						real-world chain pulling animation.
						<br />
						For each chain, a complete pull with the background color is done first so overlapping flowers are distinguishable
						by depth.
					</p>
				</span>
			</span>
		</div>
	</div>

	<div class="mx-10 mt-20">
		<h2 class="text-xl font-semibold mb-1">Color composition</h2>
		<p class="mb-2">
			A total of 40 handpicked color palettes are used throughout Petunia, with some having one set of main color and
			outlier color, some having two sets, and a few being simple linear gradients between two colors. The palettes with
			two sets have their colors distributed either based on the seperate sections of the composition, or spread in
			every section of the composition using the Perlin noise algorithm.
		</p>
	</div>

	<h2 class="text-2xl font-bold mb-1 mx-10 mt-20 text-center">Sample gallery</h2>
	<div class="grid md:grid-rows-3 md:grid-cols-4 grid-rows-6 grid-cols-2 mx-10 mt-5 gap-5">
		{#each [...Array(12).keys()] as i}
			<a href="/petunia/sample{i + 1}.png" target="_blank">
				<img class="shadow-lg shadow-black" src="/petunia/sample{i + 1}.png" alt="Sample output {i + 1}" />
			</a>
		{/each}
	</div>
</div>
