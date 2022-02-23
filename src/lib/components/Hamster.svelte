<script>
  import { fly } from 'svelte/transition';
  export let games, wins, defeats, imgName, loves, name, favFood, id, isClicked, age
</script>


<div  class="hamster--container" id={id}>
  <div on:click={() => isClicked = !isClicked}>
  {#if isClicked}
  <div class="wrapper">
    <ul in:fly="{{ y: -100, duration: 750 }}">
      <li>Favorite food: {favFood}</li> 
      <li>Age: {age}</li> 
      <li>Loves: {loves}</li>
      <li>Games: {games}</li>
      <li>Wins: {wins}</li>
      <li>Defeats: {defeats}</li>
    </ul>
  </div>
  {:else}
  <div class="wrapper">
    <img in:fly="{{ y: -500, duration: 750 }}"
    src="{`../../static/img/${imgName}`}" alt="hamster"> 
  </div>
  {/if}
  </div>
  <div id="bottom--container">
    <span id="name">{name}</span>
    <button id="delete--button">Delete</button>
  </div>
</div>


<style>
  .hamster--container {
    border-radius: 1em;
    /* border-bottom-right-radius: 0;
    border-bottom-left-radius: 0; */
    display: flex;
    flex-direction: column;
    width: 300px;
    min-height: 300px;
    overflow:hidden;
    border: 1px solid black;
    font-size: 1.5em;
    font-family: sans-serif;
  }

  .wrapper {
    height: 300px;
  }

  ul {
    list-style: none;
    margin: 0;
    padding: 0;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    font-family: sans-serif;
    font-size: 20px;
    text-align: center;
  }

  img {
    width: 100%;
    height: 300px;
    object-fit:fill;
  }

  #bottom--container {
    display: flex;
    justify-items: center;
    flex-direction: column;
    margin-top: auto;
    min-height: 70px;
    max-height: 70px;
  }

  #name {
    background-color: black;
    color: white;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 50%;
  }

  button {
    background-color: #ff0000;
    border: none;
    color: white;
    height: 50%;
    cursor: pointer;
    font-size: 1em;
  }
</style>