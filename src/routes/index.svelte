<style>
	h1, figure, p {
		text-align: center;
		margin: 0 auto;
	}

	h1 {
		font-size: 2.8em;
		text-transform: uppercase;
		font-weight: 700;
		margin: 0 0 0.5em 0;
	}

	figure {
		margin: 0 0 1em 0;
	}

	img {
		width: 100%;
		max-width: 400px;
		margin: 0 0 1em 0;
	}

	p {
		margin: 1em auto;
	}

	@media (min-width: 480px) {
		h1 {
			font-size: 4em;
		}
	}
	form,input {
		font-family: monospace;
	}
</style>

<svelte:head>
	<title>Sapper project template</title>
</svelte:head>

<form>
  phone: "{$page.query.phone}"
  <br>value<input type="text" value={$page.query.phone}>
  <br>bind:value<input type="text" bind:value={$page.query.phone}>
  <br>let<input type="text" value={phone}> should keep initial value
  <br>{JSON.stringify($page.query)}
</form>

<a href="/?phone=+123456789">/?phone=+123456789</a>
<br>
<a href="/?phone=+987654321">/?phone=+987654321</a>
<br>
<a href="/?phone=%2B123456789">/?phone=%2B123456789</a>
<br>
<a href="/?phone=%2B987654321">/?phone=%2B987654321</a>

<script>
  import { page } from '@sapper/app'

  let phone = $page.query.phone
</script>
