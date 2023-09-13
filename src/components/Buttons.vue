<template>
  <div class="buttons-collection">
      <h2>Buttons</h2>

      <section class="buttons-gallery">
        <button>Check It Out</button>
      </section>
  </div>
</template>

<script>
export default {
  name: 'Buttons',
}
</script>

<style>
.buttons-gallery {
    margin: 1rem 0;
}

button {
    background-color: var(--primary);
    color: var(--secondary);
    border-radius: var(--btnBorderRadius);
    padding: var(--btnHorPadding) var(--btnVertPadding);
}
</style>
