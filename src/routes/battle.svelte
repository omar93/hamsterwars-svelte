<script context="module">
	let key = ''

  let getConfig = {
    method: 'GET',
    mode: 'cors',
    headers: {
      'Content-Type': 'application/json',
      Authorization: 'Bearer ' + key
    }
  }

	export async function load({ fetch }) {
		const response = await fetch('http://localhost:3233/hamsters/random', getConfig)
		
		if(response.ok) {
			const hamsters = await response.json()
			return {
				props: {
					hamsters
				}
			}
		}
		return {
			status: response.status,
			error: new Error(response.status)
		}
		
	}
</script>

<script>
	import Hamster from '$lib/components/Hamster.svelte'
  export let hamsters
  console.log(hamsters);
</script>

<p>Battle page!</p>

<div class="battle-wrapper">
{#each hamsters as hamster}
	<div class="voting--wrapper">
		<Hamster {...hamster}/>
		<button>Vote!</button>
	</div>
{/each}
</div>

<style>
	.battle-wrapper {
		display: flex;
	}
</style>