<script lang="ts">
	const { children } = $props();
</script>

<p class="warning">
	{@render children?.()}
</p>

<style>
	.warning {
		margin: 8px 0 8px 0;
		padding: 4px 8px;
		background-color: #f5f1f0;
		border-left: 4px solid #cf222e;
	}
</style>
