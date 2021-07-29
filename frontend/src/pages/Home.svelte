<script>
  export let name = null
</script>

<div>
  <h1>Welcome {name ? name : 'Stranger'}!</h1>
  <p>This is the homepage!</p>
</div>

<style>
  h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
    margin: 0;
    padding: 10px 0;
	}
</style>