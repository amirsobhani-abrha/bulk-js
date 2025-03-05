<script>
	export let title;
	export let description;
	export let imgUrl;
	export let alt;
	export let ref;
</script>

<div>
	<div class=" flex flex-col md:flex-row">
		<div class="lg:w-2/5 md:w-1/4 xl:w-1/4 flex justify-center">
			<div class="w-full">
				<img class="w-full" src={imgUrl} {alt} />
			</div>
		</div>
		<div class=" lg:w-3/5 md:w-3/4 xl:w-3/4 px-4 flex flex-col justify-between py-2">
			<div>
				<h2 class="text-2xl font-bold">{title}</h2>
				<p class="inline">{description}</p>
			</div>
			<div class="space-x-4 flex justify-end my-5 md:my-0">
				<a
					href={ref}
					class="bg-[#fffbf6] text-black inline-flex items-center space-x-2 font-bold py-1 px-4 duration-300 hover:bg-black border-2 border-black hover:text-[#fffbf6]"
					><span>more</span>
					<svg
						xmlns="http://www.w3.org/2000/svg"
						viewBox="0 0 12 12"
						width="12"
						height="12"
						fill="none"
						stroke="currentColor"
						stroke-width="1.5"
						stroke-linecap="round"
						stroke-linejoin="round"
					>
						<path d="M9 2L2 9M2 2h7v7"></path>
					</svg>
				</a>
			</div>
		</div>
	</div>
</div>
