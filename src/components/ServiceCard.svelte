<script lang="ts">
	const { header, url, description, provider } = $props();
</script>

<section>
	<h3>{header}</h3>
	<p style="margin: 0">
		<code>{url}</code> | Powered by {@render provider()}
	</p>
	{@render description()}
</section>
