<script>
	async function getData(){
		const res=await fetch("https://api.github.com/users/melihuzun/repos")
		const data=await res.json()
		return data;
	}
</script>
{#await getData()}
	<p>test</p>
{:then data} 
	{#each data as repo (repo.id)}
	{#if !repo.fork && !repo.has_pages}
		<h1><a href="{repo.html_url}">{repo.name}</a></h1>
		{#if repo.description}
			<p>{repo.description}</p>
		{:else}
		<p>This repo have any description</p>
		{/if}
	{/if}
	{/each}
{/await}