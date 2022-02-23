<header>
  <h1>Welcome to Hamster wars</h1>
  <div id="links">
    <a href="/">Start</a>
    <a href="/battle">Battle</a>
    <a href="/gallery">Gallery</a>
    <a href="/add">Add new hamster</a>
  </div>
  <span>You can get information about the hamster by clicking on one of them</span>
</header>

<style>
  header {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    font-family: sans-serif;
  }
  header > * {
    margin-bottom: 10px;
  }

  h1 {
    font-size: 4em;
  }

  #links {
    width: 30%;
    display: flex;
    justify-content: space-evenly;
  }

  span {
    font-size: 3em;
  }

  a {
    font-size: 1.5em;
  }
</style>