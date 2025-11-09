<script lang="ts">
	import ServiceCard from './ServiceCard.svelte';
	import Warning from './Warning.svelte';
</script>

<main>
	<section style="width: 38%; min-width: 380px">
		<h1>About SourLemonJuice.net</h1>
		<p>
			This is a domain name of 酸柠檬猹/SourLemonJuice.<br />
			Some random web projects will be deployed here. Like Google, subdomains are a good thing.
		</p>
		<p>
			To be clear, I would not use this domain as an online documentation for my own projects.<br />
			I trust GitHub Pages but not something I control...
		</p>
		<p>
			Servers cost money and require constant maintenance. As is the case with this index page, pure HTML services will
			deployed on Cloudflare Pages, Which I suppose is the best solution...<br />
			I'm still hoping that in the future I can be able to put it to the value it deserves, I guess.
		</p>
		<p>
			Also, this domain will not replace the
			<a href="https://sourlemonjuice.github.io/SourLemonJuice-blog/"><strong>SourLemonJuice-blog</strong></a>, that's
			my main site.
		</p>
	</section>
	<section style="width: 62%; min-width: 300px">
		<h2>Services Reference</h2>
		<ServiceCard header="Connectivity Test" url="https://connectivity.sourlemonjuice.net">
			{#snippet provider()}
				<a href="https://caddyserver.com">Caddy</a>
			{/snippet}
			{#snippet description()}
				<p>
					This domain will always connect to my cloud server instead of CDN. Maybe some system calls them captive
					portal, like Android's <code>captive_portal_http_url</code>.<br />
					This API can be used just like
					<a href="https://connectivitycheck.gstatic.com/generate_204">connectivitycheck.gstatic.com/generate_204</a>,
					which is used by a lot of Android devices.
				</p>
				<table>
					<thead>
						<tr>
							<th scope="col">URI</th>
							<th scope="col">Return status</th>
							<th scope="col">Meaning</th>
						</tr>
					</thead>
					<tbody>
						<tr>
							<td><code>/generate_204</code></td>
							<td>204 No Content</td>
							<td>the simplest one, preferred this</td>
						</tr>
						<tr>
							<td><code>/generate_200</code></td>
							<td>200 OK</td>
							<td>only guarantees that the content is not empty</td>
						</tr>
						<tr>
							<td><code>/NetworkManager</code></td>
							<td>200 OK</td>
							<td>
								follow the "connectivity section" in <a
									href="https://networkmanager.pages.freedesktop.org/NetworkManager/NetworkManager/NetworkManager.conf.html"
								>
									NetworkManager.conf(5)
								</a>
							</td>
						</tr>
					</tbody>
				</table>
				<Warning>
					{#snippet content()}
						Before 2025-02-27, this domain was <code>https://connection.sourlemonjuice.net</code>
					{/snippet}
				</Warning>
			{/snippet}
		</ServiceCard>
		<ServiceCard header="Redirect" url="https://goto.sourlemonjuice.net">
			{#snippet provider()}
				Cloudflare Worker with my
				<a href="https://github.com/SourLemonJuice/redirect-worker">redirect-worker</a>
			{/snippet}
			{#snippet description()}
				<p>
					Like <a href="https://aka.ms">aka.ms</a> or <a href="https://goo.gle">goo.gle</a>, it's a regular short link
					service. But where would I link to? The fourth dimension space, probably.
				</p>
			{/snippet}
		</ServiceCard>
		<ServiceCard header="DNS over HTTPS Forwarding [Experimental]" url="https://dns-next.sourlemonjuice.net">
			{#snippet provider()}
				Cloudflare Worker with my <a href="https://github.com/SourLemonJuice/doh-forward-worker">doh-forward-worker</a>
			{/snippet}
			{#snippet description()}
				<p>
					Use Cloudflare DNS(HTTPS) as upstream.<br />
					Your request will be logged via Cloudflare Worker Observability. We will disable logging of sensitive information
					after the experimental phase.
				</p>
			{/snippet}
		</ServiceCard>
		<ServiceCard header="DNS Recursive Server [Discontinued]" url="dns.sourlemonjuice.net">
			{#snippet provider()}
				<a href="https://www.nlnetlabs.nl/projects/unbound/about/">Unbound</a>
			{/snippet}
			{#snippet description()}
				<p>
					DNS recursive server runs on <code>dns.sourlemonjuice.net</code> with regular port 53/853/443, means it
					supports Plain DNS, DNS-over-TLS and DNS-over-HTTPS.<br />
					It's not just a request forward but a recursive server. As for the DNS-over-QUIC, that's not in the plan.
				</p>
				<p>
					We promise won't use your data and IP information for purposes other than querying and not to store any logs.
					However, we don't provide any form of guarantee and do not assume any legal liability for data leakage.
				</p>
				<Warning>
					{#snippet content()}
						Service discontinued after 2025-11-09
					{/snippet}
				</Warning>
			{/snippet}
		</ServiceCard>
	</section>
</main>

<style>
	main {
		max-width: 1440px;
		width: 100%;
		margin-bottom: 16px;
		display: flex;
		flex-direction: row;
		align-items: flex-start;
		justify-content: center;
	}

	section {
		margin-inline: 4px;
	}
</style>
