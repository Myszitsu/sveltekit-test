<script context="module">
	export async function load({ fetch, page }) {
		const id = page.params.id;
		const res = await fetch(`https://jsonplaceholder.typicode.com/posts/${id}`);
		const guide = await res.json();
		if (res.ok) {
			return {
				props: {
					guide,
				},
			};
		}

		return {
			status: 301,
			redirect: '/guides'
		};
	}
</script>

<script>
	export let guide;
</script>

<div class="guide">
	<h2>{guide.title}</h2>
	<p>{guide.body}</p>
</div>

<style>
	.guide {
		margin-top: 40px;
		padding: 10px;
		border: 1px solid rgba(0, 0, 0, 0.2);
	}
</style>
