<script lang="ts">
	let {
		'aria-label': ariaLabel,
		onclick,
		...rest
	}: {
		'aria-label'?: string;
		onclick?: () => void;
		[k: string]: unknown;
	} = $props();
</script>

<button data-test={rest['data-test']} aria-label={ariaLabel} {onclick}>MoreButton</button>
