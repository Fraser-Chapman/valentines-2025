<script lang="ts">
	import { browser } from '$app/environment';

	if (browser) {
		const noButton: HTMLButtonElement = document.getElementById('no-button') as HTMLButtonElement;

		if (noButton) {
			noButton.addEventListener('click', () => {
				document.body.setAttribute('data-theme', 'nasty-theme');
			});
		}
	}
</script>
<div class="container h-full mx-auto flex justify-center items-center">
	<div class="space-y-10 text-center flex flex-col items-center">
		<h2 class="h2">Will you be my valentine?</h2>
		<div class="flex justify-center space-x-2">
			<div class="btn variant-filled">
				Yes
			</div>
			<div class="btn variant-filled" id="no-button">
				No
			</div>
		</div>
	</div>
</div>
