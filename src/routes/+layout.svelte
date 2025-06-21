<script>import "../app.css";
import Footer from "./footer.svelte";
import Header from "./top_header.svelte"</script>

<Header></Header>
	
<main>
<slot></slot></main>

<Footer></Footer>


<style>
	#root {
		display: flex;
		flex-direction: column;
		margin: 10px;
		border-radius: 10px;
	}

	hr {
		width: 99%;
		border: 1px solid #333;
	}
	#root {
    display: flex;
    flex-direction: column;
    min-height: 100vh; /* Takes up at least the full viewport height */
  }

  main {
    flex-grow: 1; /* This is the magic part! */
    /* It tells the main content area to grow and take up all available */
    /* space, pushing the footer to the bottom. */
  }
</style>
