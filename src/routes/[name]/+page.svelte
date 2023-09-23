<script>
	export let data;
</script>

<svelte:head>
	<title>{data.name}'s page</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<main class="w-screen h-screen grid p-8">
	<img
		class="ball h-96 shadow-sm rounded-full"
		src="/{data.name}.jpeg"
		alt=""
	/>
</main>

<style>
	main {
		--s: 200px; /* control the size */
		--c: #fff; /* first color */

		--_g: #0000 8%, var(--c) 0 17%, #0000 0 58%;
		background: linear-gradient(
					135deg,
					#0000 20.5%,
					var(--c) 0 29.5%,
					#0000 0
				)
				0 calc(var(--s) / 4),
			linear-gradient(45deg, var(--_g)) calc(var(--s) / 2) 0,
			linear-gradient(135deg, var(--_g), var(--c) 0 67%, #0000 0),
			linear-gradient(
				45deg,
				var(--_g),
				var(--c) 0 67%,
				#0000 0 83%,
				var(--c) 0 92%,
				#0000 0
			),
			#1095c1; /* second color */
		background-size: var(--s) var(--s);
	}

	.ball {
		animation: bounce 5s infinite cubic-bezier(0.165, 0.84, 0.44, 1);
	}

	@keyframes bounce {
		0% {
			transform: translate3d(0, 0, 0);
		}
		25% {
			transform: translate3d(50vw, calc(100vh - 24rem), 0) rotate(180deg);
		}
		50% {
			transform: translate3d(100vw, 0, 0) rotate(360deg);
		}
		75% {
			transform: translate3d(200px, calc(100vh - 24rem), 0) rotate(180deg);
		}
		100% {
			transform: translate3d(0, 0, 0) rotate(360deg);
		}
	}
</style>
