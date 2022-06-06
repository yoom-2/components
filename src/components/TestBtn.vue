<template>
  <div class="btn">
    <button class="click-btn" @click="handleBtn">Click</button>
  </div>

</template>
<script>
export default {
  methods: {
    handleBtn($event) {
      this.$emit('click', $event.target.value);
    },
  }
}
</script>
<style>
  .btn {
    width: 100%;
    text-align: right;
    padding-top: 10px;
  }
  .click-btn {
    width: 150px;
    height: 25px;
    background-color: antiquewhite;
    border: 0;
    color: #333333;
  }
</style>
