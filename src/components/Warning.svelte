<script lang="ts">
	const { content } = $props();
</script>

<p class="warning">
	Warning: {@render content()}
</p>

<style>
	.warning {
		margin: 8px 0 8px 0;
		padding: 4px 12px;
		background-color: #f5f1f0;
		border-left: 4px solid #cc6649;
	}
</style>
