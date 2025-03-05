<svelte:head>
	<title>S&J | Purpose in Motion</title>
	<meta name="description" content="Movement - a generative art project by S&J" />
</svelte:head>

<div class="container md:w-4/5 mx-auto my-10">
	<h1 class="text-2xl font-bold mx-10">Purpose in Motion</h1>
	<h2 class="mb-10 mx-10">An exploration of cooperating components</h2>

	<div class="grid mx-10 mb-20 gap-10">
		<a href="/pim/moving.gif" target="_blank">
			<img class="shadow-2xl shadow-black mx-auto" src="/pim/moving.gif" alt="Dynamic output" />
		</a>
		<div>
			<h2 class="text-xl font-semibold mb-3 text-center">The concept</h2>
			<p class="mb-2">
				Cogs in a system are constantly turning, affecting not only themselves, but the entire system as a whole.
			</p>
			<p class="mb-2">
				No cog is aware of its own role in the system's function, nor does it need to. It only needs to drive or be
				driven. It does not care wether it is contributing to a greater good than its own turning, or if it is just
				turning to no end.
			</p>
			<p>
				What we tried to achieve in this work was to present this question to the viewer. The answer to it is left up to
				the viewer's perspective, and may ultimately lead - or be derived from - the viewer's philosophy of a person's
				meaning and direction in life and society. Are we just going through our day to day cycles without knowing or
				caring where it is taking us, or are we aware of our contribution to an end bigger than ourselves?
			</p>
		</div>
	</div>

	<div class="mx-10">
		<h2 class="text-xl font-semibold mb-0 text-center">The approach</h2>
		<p class="mb-3 text-center">Implemented in p5.js and GLSL, Purpose in Motion utilizes both the CPU and the GPU.</p>
		<div class="flex md:flex-row flex-col my-10 gap-5">
			<span class="md:w-1/2">
				<h3 class="text-lg">The CPU</h3>
				<p class="mb-3">
					A randomly set number of gears with different numbers of teeth are placed on the canvas, each rotated so that
					the teeth lock into each other.
					<br />
					The direction and speed ratio of every gear's rotation is then calculated, by taking one gear as the driver and
					all the others as driven.
					<br />
					Finally, geometry models are created from the gears and the models are passed to shaders in order to come to life.
				</p>
			</span>
			<a class="md:w-1/2" href="/pim/cpu.png" target="_blank">
				<img class="shadow-2xl shadow-black" src="/pim/cpu.png" alt="An output utilizing only the CPU" />
			</a>
		</div>

		<hr class="md:hidden block border-1 border-gray-300" />
		<div class="flex md:flex-row flex-col-reverse my-10 gap-5">
			<a class="md:w-1/2" href="/pim/gpu.png" target="_blank">
				<img class="shadow-2xl shadow-black" src="/pim/gpu.png" alt="An output utilizing both the CPU and the GPU" />
			</a>
			<span class="md:w-1/2">
				<h3 class="text-lg">The GPU</h3>
				<p>
					The GPU takes the composing vertices of each gear as inputs for the vertex shaders and then displaces those
					vertices to account for the gear's rotation, based on the current time (passed since the sketch started),
					direction and speed ratio. The dislocated vertices are then passed to fragment shaders, which apply outline
					strokes, textures and shadows to the composed shapes.
					<br />
					<br />
					The shadows are composed of individual lines instead of a traditional uniform shadow, and the length of each line
					is calculated based on the current position of the light source, its angle with each point on the shape, and the
					height of the gears' faces.
				</p>
			</span>
		</div>

		<hr class="md:hidden block border-1 border-gray-300" />
		<div class="grid my-10 gap-5">
			<span>
				<h3 class="text-lg">The final touch</h3>
				<p>
					Using shaders again, a steam filter is applied to the entire image, and solid color borders are placed on the
					four sides.
				</p>
			</span>
			<a href="/pim/finished.png" target="_blank">
				<img class="shadow-2xl shadow-black" src="/pim/finished.png" alt="A finished output" />
			</a>
		</div>
	</div>

	<div class="mx-10 mt-20">
		<h2 class="text-xl font-semibold mb-1">Color composition</h2>
		<p class="mb-2">
			There are three types of color compositions used in Purpose in Motion; Light - the most common, dark and
			blueprint. We avoided using vibrant and eye-catching colors, in order to better keep the outputs in line with the
			theme of monotony and repetition.
			<br />
			There are also two more elements used throughout the work: a moving steam filter, and the movement of the light source.
			These elements were added to very roughly emulate the passage of time and its ravage on the gears and their environment.
		</p>
	</div>
	<div class="grid md:grid-rows-1 md:grid-cols-3 grid-rows-3 mx-10 mt-5 gap-10">
		<a href="/pim/finished.png" target="_blank">
			<img class="shadow-2xl shadow-black" src="/pim/finished.png" alt="Light color composition" />
		</a>
		<a href="/pim/dark.png" target="_blank">
			<img class="shadow-2xl shadow-black" src="/pim/dark.png" alt="Dark color composition" />
		</a>
		<a href="/pim/blue.png" target="_blank">
			<img class="shadow-2xl shadow-black" src="/pim/blue.png" alt="Blueprint color composition" />
		</a>
	</div>

	<h2 class="text-2xl font-bold mb-1 mx-10 mt-20 text-center">Sample gallery (static)</h2>
	<div class="grid md:grid-rows-4 md:grid-cols-3 grid-rows-6 grid-cols-2 mx-10 mt-5 gap-5">
		{#each [...Array(12).keys()] as i}
			<a href="/pim/sample{i + 1}.png" target="_blank">
				<img class="shadow-lg shadow-black" src="/pim/sample{i + 1}.png" alt="Sample output {i + 1}" />
			</a>
		{/each}
	</div>
</div>
