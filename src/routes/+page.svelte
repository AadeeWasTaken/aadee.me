<script lang="ts">
	let twitterHover: boolean = false;
	let githubHover: boolean = false;
	let linkedinHover: boolean = false;

	const socialMedia: {
		name: string;
		link: string;
		hover: () => boolean;
		unhover: () => boolean;
	}[] = [
		{
			name: 'twitter',
			link: 'https://twitter.com/AadeeWasTaken',
			hover: () => (twitterHover = true),
			unhover: () => (twitterHover = false)
		},
		{
			name: 'github',
			link: 'https://github.com/AadeeWasTaken',
			hover: () => (githubHover = true),
			unhover: () => (githubHover = false)
		},
		{
			name: 'linkedin',
			link: 'https://www.linkedin.com/in/aadee/',
			hover: () => (linkedinHover = true),
			unhover: () => (linkedinHover = false)
		}
	];
</script>

<svelte:head>
	<title>Aadee - (Hover Over The Name)</title>
</svelte:head>

<div class="h-screen w-screen font-display text-white">
	<div class="h-screen flex flex-col space-y-20 justify-center items-center">
		<div class="flex justify-center items-center">
			{#if twitterHover || githubHover || linkedinHover}
				<ul class="flex space-x-14 text-9xl cursor-default">
					{#each twitterHover ? 'TWITTER' : githubHover ? 'GITHUB' : 'LINKEDIN' as letter}
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
				{#each socialMedia as social}
					<li>
						<a
							href={social.link}
							target="_blank"
							rel="noopener noreferrer"
							class="underline underline-offset-4 p-2 hover:bg-white hover:text-black hover:no-underline"
							on:mouseenter={() => social.hover()}
							on:mouseleave={() => social.unhover()}>{social.name}</a
						>
					</li>
				{/each}
			</ul>
		</div>
	</div>
</div>

<style lang="postcss">
	:global(html) {
		background-color: theme(colors.black);
	}
</style>
