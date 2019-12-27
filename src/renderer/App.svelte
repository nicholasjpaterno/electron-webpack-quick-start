<script>
  export let makeCall;
  export let name;
  import { fly } from 'svelte/transition';
  $: count = 0;
  import Header from "./Header.svelte";
</script>

<Header/>
<div>Hello {name}!</div>
<button on:click={() => {makeCall();count++;}} color="primary">click</button>
<p>COOL {count}</p>
{#if count % 2}
  <div transition:fly="{{delay: 250, duration: 300, x:10, y: 10}}">
    fades in and out
  </div>
{/if}