<script>
  import {navigate} from 'svelte-routing'

  let isSubmitting = false

  $: disabled = isSubmitting

  function handleSubmit() {
    isSubmitting = true

    setTimeout(() => {
      isSubmitting = false
      navigate("/checkout/confirm")
    }, 3000)
  }
</script>
<form on:submit|preventDefault={handleSubmit}>
  <h2>Payment</h2>

  <button {disabled}>
    {isSubmitting ? "Submitting..." : "Continue"}
  </button>
</form>
