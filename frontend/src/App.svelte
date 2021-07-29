<script>
	import { Router, Route, Link } from 'svelte-navigator'
	import Home from './pages/Home.svelte'
	import About from './pages/About.svelte'
	import Header from './components/Header.svelte'
	import NotFound from './components/NotFound.svelte'

	let name = null
	let isFetching = false

	const fetchData = async () => {
		isFetching = true
		try {
			const response = await fetch('http://localhost:8000',);
			const result = await response.json()
			console.log(result)
			name = result.message
			isFetching = false
		} catch(e) {
			console.error(e)
			isFetching = false
		}
	}
	fetchData()
</script>

<Router>
	<Header />

	<main>
		<div>
			<Route path="/">
				<Home {name}/>
			</Route>

			<Route path="/about">
				<About />
			</Route>

			<Route>
				<NotFound />
			</Route>
		</div>
	</main>
</Router>

<style>
	main {
		text-align: center;
		height: 93vh;
		width: 100%;
	}
</style>