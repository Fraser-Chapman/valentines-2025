<script lang="ts">
	import '../app.postcss';
	import { AppShell } from '@skeletonlabs/skeleton';
</script>

<!-- App Shell -->
<AppShell>
	<svelte:fragment slot="header">
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
</AppShell>
