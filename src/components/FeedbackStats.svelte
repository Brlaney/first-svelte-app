<script>
  export let count
  export let ave
</script>

<div class='feedback-stats'>
  <h4>Number of reviews: {count}</h4>
  <h4>Ratings average: {ave}</h4>
</div>

<style>
  .feedback-stats {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
</style>
