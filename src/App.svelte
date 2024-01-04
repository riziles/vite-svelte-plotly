<script lang="ts">
  import svelteLogo from './assets/svelte.svg'
  import plotlylogo from './assets/plotly-logo-vector.svg'
  import viteLogo from '/vite.svg'
  import Plotly from 'plotly.js-dist-min'

  let tester:HTMLElement

  let val = 12

  $: {if (tester ){
      Plotly.react(tester, /* JSON object */ {
            "data": [{ "y": [1, val, 30] }],
            "layout": { "width": 600, "height": 400}
        })
    }}
</script>

<main>

  <h1>Vite + Svelte + Plotly</h1>

  <input type="range" min="-10" max="50" bind:value={val}>

  <div bind:this={tester} id="tester" style="width:600px;height:500px;"></div>

  <div>
    <a href="https://vitejs.dev" target="_blank" rel="noreferrer">
      <img src={viteLogo} class="logo" alt="Vite Logo" />
    </a>
    <a href="https://svelte.dev" target="_blank" rel="noreferrer">
      <img src={svelteLogo} class="logo svelte" alt="Svelte Logo" />
    </a>
    <a href="https://plotly.com/graphing-libraries/" target="_blank" rel="noreferrer">
      <img src={plotlylogo} class="logo svelte" alt="Svelte Logo" />
    </a>
  </div>

</main>

<style>
  .logo {
    height: 4em;
    padding: 1.5em;
    will-change: filter;
    transition: filter 300ms;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
</style>
