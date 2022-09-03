<template>
  <div class="card">
    <slot />
  </div>
</template>

<script>
export default {
  name: "Card"
}
</script>

<style>
.card {
  justify-self: center;
  display: flex;
  flex-direction: column;
  width: 320px;
  overflow: hidden;
  box-shadow: 0px 4px 10px 3px #94949440;
  border-radius: 20px;
}

@media (min-width: 576px) and (max-width: 768px) {
  .card {
    width: 380px;
  }
}

@media (min-width: 1400px) {
  .card {
    width: 380px;
  }
}
</style>
