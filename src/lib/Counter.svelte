<script>
  let count = 0
  const increment = () => {
    count += 1
  }
  const reset = () => {
    count = 0
  }
</script>

<button on:click={increment}>
  count is {count}
</button>
<button on:click={reset}>
  Reset counter
</button>
