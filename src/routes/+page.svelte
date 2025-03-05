<script>
	import Project from '../lib/Project.svelte';
</script>

<svelte:head>
	<title>S&J - Generative art duo</title>
	<meta name="description" content="Generative art duo" />
</svelte:head>

<div id="background-container" class=" flex flex-col justify-center">
	<div class="container mx-auto h-60 bg-[#fffbf6] w-3/4 flex justify-center flex-col">
		<p class="text-center font-bold text-6xl">Capturing life on the screen</p>
	</div>
</div>
<div class="container mx-auto px-8 py-8 flex font-bold justify-center">
	<h1>Projects</h1>
</div>
<div class="container mx-auto px-8 py-2 lg:flex">
	<div class="lg:w-1/2 lg:mr-4 mb-8 lg:mb-0 border border-black">
		<Project
			title="Petunia"
			description="Simulation of chain pull technique for painting flowers"
			imgUrl="homepage/petuniaCover.png"
			alt="Cover output"
			ref="/petunia"
		/>
	</div>

	<div class="lg:w-1/2 lg:ml-4 border border-black">
		<Project
			title="Purpose in Motion"
			description="Moving systems of cogwheels"
			imgUrl="homepage/pimCover.png"
			alt="Cover output"
			ref="/purpose-in-motion"
		/>
	</div>
</div>
<div class="container mx-auto p-8 lg:flex">
	<div class="lg:w-1/2 lg:mr-4 mb-8 lg:mb-0 border border-black">
		<Project
			title="Shams"
			description="Achieving perfection"
			imgUrl="homepage/shamsCover.png"
			alt="Cover output"
			ref="/shams"
		/>
	</div>

	<div class="lg:w-1/2 lg:ml-4"></div>
</div>

<div class="container mx-auto px-8 py-8 flex font-bold justify-center">
	<h1 class="text-center">About</h1>
</div>
<div class="container py-8 px-8 text-lg">
	<p>
		S&J are an up-and-coming generative art duo, using their prior experience in software engineering and web-based
		programming to create visual works of art mainly through Javascript code. We try to capture moments of life in our
		art, urging the viewer to give a sort of more depthful thought to ordinary every-day occasions and landscapes.
		<br />
		<br />
		Having an educational and career background of computer science, along the way we experimented with small-scale video
		game development engines, node-based visual programming frameworks, and shader languages (e.g. Unity, Blender, TouchDesginer
		and GLSL). These experiments piqued our interest in using programming as a tool to create visual works of art, veering
		us away from developing traditional software and towards generative art.
	</p>
</div>

<style>
	/* Style the h1 tag with lines before and after */
	h1 {
		position: relative;
		display: inline-block;
		font-size: 1.5rem; /* Adjust the font size as needed */
	}

	h1::before,
	h1::after {
		content: '';
		position: absolute;
		height: 1px;
		width: 40px; /* Adjust the line length as needed */
		background-color: #333; /* Adjust the line color as needed */
		top: 50%;
		transform: translateY(-50%);
	}
	h1::before {
		left: -60px; /* Adjust the spacing before the text */
	}

	h1::after {
		right: -60px; /* Adjust the spacing after the text */
	}

	#background-container {
		height: 500px; /* Set your desired height */
		background-image: url('/homepage/svgviewer-output.svg');
		background-repeat: repeat-x;
	}

	/* Style the container */
</style>
