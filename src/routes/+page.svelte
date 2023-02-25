<script lang="ts">
	let twitterHover: boolean = false;
	let githubHover: boolean = false;
	let linkedinHover: boolean = false;

	let twitterHovered = () => (twitterHover = true);
	let twitterUnhovered = () => (twitterHover = false);

	let githubHovered = () => (githubHover = true);
	let githubUnhovered = () => (githubHover = false);

	let linkedinHovered = () => (linkedinHover = true);
	let linkedinUnhovered = () => (linkedinHover = false);
</script>

<svelte:head>
	<title>Aadee - (Hover Over The Name)</title>
</svelte:head>

<div class="h-screen w-screen font-display text-white">
	<div class="h-screen flex flex-col space-y-20 justify-center items-center">
		<div class="flex justify-center items-center">
			{#if twitterHover}
				<ul class="flex space-x-14 text-9xl cursor-default">
					{#each 'TWITTER' as letter}
						<li class="bg-white text-black">
							{letter}
						</li>
					{/each}
				</ul>
			{:else if githubHover}
				<ul class="flex space-x-14 text-9xl cursor-default">
					{#each 'GITHUB' as letter}
						<li class="bg-white text-black">
							{letter}
						</li>
					{/each}
				</ul>
			{:else if linkedinHover}
				<ul class="flex space-x-14 text-9xl cursor-default">
					{#each 'LINKEDIN' as letter}
						<li class="bg-white text-black">
							{letter}
						</li>
					{/each}
				</ul>
			{:else}
				<h1>
					<ul class="flex space-x-14 text-9xl cursor-default">
						{#each 'aadee' as letter}
							<li class="hover:uppercase hover:bg-white hover:text-black">
								{letter}
							</li>
						{/each}
					</ul>
				</h1>
			{/if}
		</div>
		<div class="flex justify-center">
			<ul class="flex space-x-14">
				<li>
					<a
						href="https://twitter.com/AadeeWasTaken"
						target="_blank"
						rel="noopener noreferrer"
						class="underline underline-offset-4 p-2 hover:bg-white hover:text-black hover:no-underline"
						on:mouseenter={() => twitterHovered()}
						on:mouseleave={() => twitterUnhovered()}>twitter</a
					>
				</li>
				<li>
					<a
						href="https://github.com/AadeeWasTaken"
						target="_blank"
						rel="noopener noreferrer"
						class="underline underline-offset-4 p-2 hover:bg-white hover:text-black hover:no-underline"
						on:mouseenter={() => githubHovered()}
						on:mouseleave={() => githubUnhovered()}>github</a
					>
				</li>
				<li>
					<a
						href="https://www.linkedin.com/in/aadee/"
						target="_blank"
						rel="noopener noreferrer"
						class="underline underline-offset-4 p-2 hover:bg-white hover:text-black hover:no-underline"
						on:mouseenter={() => linkedinHovered()}
						on:mouseleave={() => linkedinUnhovered()}>linkedin</a
					>
				</li>
			</ul>
		</div>
	</div>
</div>

<style lang="postcss">
	:global(html) {
		background-color: theme(colors.black);
	}
</style>
