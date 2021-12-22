<script>
  import {createEventDispatcher} from 'svelte'
  import Card from './Card.svelte'
  export let item

  const dispatch = createEventDispatcher()

  const handleDelete = (itemId) => {
    dispatch('delete-feedback', itemId)
  }
</script>

<Card>
  <div class='num-display'>
    {item.rating}
  </div>
  <button class='close' on:click={() => handleDelete(item.id)}>
    X
  </button>
  <p class='text-display'>
    {item.text}
  </p>
</Card>

<style>
  .num-display {
    position: absolute;
    top: -10px;
    left: -10px;
    width: 50px;
    height: 50px;
    /* background: #ff6a95; */
    background: #23CE6B;
    color: #fff;
    border: 1px #eee solid;
    border-radius: 50%;
    padding: 10px;
    text-align: center;
    font-size: 19px;
  }

  .close {
    position: absolute;
    top: 10px;
    right: 20px;
    padding: 2px;
    cursor: pointer;
    border: 0;
    background: transparent;
    font-weight: bold;
    color: #50514F;
  }

  .text-display {
    color: #272D2D;
    padding: 0.4rem 0.7rem 0.1rem 0.7rem;
  }
</style>
