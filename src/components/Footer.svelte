<footer>
	<nav>
		<section class="group">
			<h2>Web services</h2>
			<ul>
				<li><a href="https://git.sourlemonjuice.net/">Gitea(Git)</a></li>
				<li><a href="https://status.sourlemonjuice.net/">Services status</a></li>
			</ul>
		</section>
		<section class="group">
			<h2>Infrastructures</h2>
			<ul>
				<li>↑Above↑</li>
			</ul>
		</section>
		<section class="group">
			<h2>About me</h2>
			<ul>
				<li><a href="https://github.com/SourLemonJuice">GitHub</a></li>
				<li><a href="https://blog.sourlemonjuice.net/">SourLemonJuice-blog</a></li>
				<li><a href="https://blog.sourlemonjuice.net/about/contacts">More contacts</a></li>
			</ul>
		</section>
	</nav>
	<p class="sidenote">
		Powered by Astro + Svelte<br />
		frontend, strange... @_@<br />
		<a href="https://github.com/SourLemonJuice/sourlemonjuice.net-re">source code</a>
	</p>
</footer>

<style>
	footer {
		max-width: 1440px;
		width: 100%;
		min-height: 128px;
		margin-bottom: 12px;
		border-top: 2px solid;
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: space-between;
	}

	nav {
		flex: 0 870px;
		display: flex;
		flex-direction: row;
		align-items: start;
		justify-content: start;
	}

	.group {
		margin: 0;
		padding: 0 32px;
	}

	.group h2 {
		font-size: large;
		font-weight: bold;
		margin: 8px 0;
	}

	.group ul {
		list-style: '';
		margin: 0 0;
		padding-left: 0;
	}

	.group li {
		margin: 6px 0;
	}

	.sidenote {
		margin: 0;
		text-align: right;
	}

	@media screen and (max-width: 740px) {
		footer {
			display: block;
		}

		nav {
			flex-direction: column;
			width: 100%;
			padding: 8px 0;
		}

		.group {
			padding: 0;
		}

		.sidenote {
			text-align: right;
			border-top: 1px solid;
			padding: 8px 0;
		}
	}
</style>
