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
		const response = await fetch('http://localhost:3233/hamsters/', getConfig)
		
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

  export let hamsters = []

  //  in:fly="{{ y: -500, duration: 750 }}"
</script>

<div id="gallery--container" >
{#each hamsters as hamster}
    <Hamster {...hamster}/>
{/each}
</div>


<style>
  #gallery--container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 10px;
  }
</style>
