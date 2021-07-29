<script>
  import { useNavigate } from 'svelte-navigator'
  import { fade } from 'svelte/transition'
  const navigate = useNavigate();
</script>

<div class="header">
  <h1 class="title" on:click="{() => navigate("/")}">Family Calendar</h1>
  <div class="navbar">
    <button transition:fade on:click="{() => navigate("/")}">Home</button>
    <button on:click="{() => navigate("/about")}">About us</button>
    <button on:click="{() => navigate("/contact")}">Contact</button>
  </div>
</div>

<style>
  .header{
    width: 100%;
    height: 7vh;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    background-color: #00173d;
  }

  .navbar{
    width: 50%;
    display: flex;
    justify-content: space-around;
    align-items: center;
  }

  .title{
    padding-left: 2%;
    margin: 0;
    color: #ff3e00;
		text-transform: uppercase;
		font-size: 3em;
		font-weight: 100;
    letter-spacing: 5px;
    cursor: pointer;
  }

  button {
    padding: 10px 25px;
    background-color: #00173d;
    border: 0px solid black;
    border-radius: 15px;
    color: #ff3e00;
    font-size: 1.5em;
    cursor: pointer;
  }

  button:hover {
    background-color: #003283;
    color: #cc3300;
  }
</style>