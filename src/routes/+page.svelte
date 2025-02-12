<script lang="ts">
	import { browser } from '$app/environment';
	import { gsap } from 'gsap';
	import { onMount } from 'svelte';

	let el1: HTMLElement;
	let el2: HTMLElement;
	let el3: HTMLElement;
	let el4: HTMLElement;
	let elements: HTMLElement[] = [];

	onMount(() => {
		elements = [el1, el2, el3, el4];
	})

	if (browser) {
		const noButton: HTMLButtonElement = document.getElementById('no-button') as HTMLButtonElement;
		const yesButton = document.getElementById('yes-button') as HTMLButtonElement;

		if (noButton) {
			noButton.addEventListener('click', () => {
				document.body.setAttribute('data-theme', 'nasty-theme');

				elements.forEach((el: HTMLElement) => {el.hidden = false});

				gsap.to(elements, {
					x: 'random(-250vw, 250vw)',
					y: 'random(-250vh, 250vh)',
					rotation: 'random(-180, 180)',
					scale: '25',
					duration: 3,
					repeat: -1,
					yoyo: true,
					ease: 'power1.inOut'
				});

			});
		}

		if (yesButton) {
			yesButton.addEventListener('click', () => {
				elements.forEach((el: HTMLElement) => {el.hidden = true});

				document.body.setAttribute('data-theme', 'nice-theme');
			});
		}
	}
</script>
<div class="container h-full mx-auto flex justify-center items-center">
	<div class="space-y-10 text-center flex flex-col items-center">

		<div class="flex-box">
			<div hidden="hidden" bind:this={el1} class="floating">🔥</div>
			<div hidden="hidden" bind:this={el2} class="floating">😡</div>
			<div hidden="hidden" bind:this={el3} class="floating">🖕</div>
			<div hidden="hidden" bind:this={el4} class="floating">OMG!</div>
		</div>

		<h2 class="h2">Will you be my valentine?</h2>
		<div class="flex justify-center space-x-2">
			<div class="btn variant-filled" id="yes-button">
				Yes
			</div>
			<div class="btn variant-filled" id="no-button">
				No
			</div>
		</div>
	</div>
</div>

<style>
    .floating {
        position: absolute;
        top: 50%;
        left: 50%;
				pointer-events: none;
    }
</style>
