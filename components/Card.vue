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
  display: flex;
  flex-direction: column;
  width: clamp(30rem, calc(20rem + 2vw), 22rem);
  margin: 0 35px;
  /*//width: fit-content;*/
  overflow: hidden;
  box-shadow: 0px 4px 10px 3px #94949440;
  /*box-shadow: 0 .1rem 1rem rgba(0, 0, 0, 0.1);*/
  border-radius: 20px;
  /*background: #ECE9E6;*/
  /*background: linear-gradient(to right, #FFFFFF, #ECE9E6);*/
}
</style>
