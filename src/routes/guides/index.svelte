<script context='module'>
	export async function load({fetch}) {
		const res = await fetch('https://jsonplaceholder.typicode.com/posts')
		const guides = await res.json()
		if (res.ok) {
			return {
				props: {
					guides
				}
			}
		}

		return {
			status: res.status,
			error: new Error('Could not fetch data')
		}
	}
</script>

<script>
	export let guides
</script>

<div class="guides">
	<ul>
		{#each guides as guide (guide.id) }
			<li>
				<a sveltekit:prefetch href="/guides/{guide.id}">{guide.title}</a>
			</li>
		{/each}
	</ul>
</div>

<style>
	.guides {
		margin-top: 20px;
	}

	ul {
		flex-direction: column;
	}
</style>
