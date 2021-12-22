<script>
  import { onMount } from 'svelte';
  import {MDCRipple} from '@material/ripple';

  onMount(() => {
    // Code goes here
    const buttonRipple = new MDCRipple(document.getElementById(id));
  })

  export let id;
  export let text;
  export let onClickFunction;
</script>

<div class='mdc-touch-target-wrapper'>
  <button class='mdc-button mdc-button--touch' {id} on:click={onClickFunction}>
    <span class='mdc-button__ripple' />
    <span class='mdc-button__touch' />
    <span class='mdc-button__label'>{text}</span>
  </button>
</div>
