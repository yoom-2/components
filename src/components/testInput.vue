<template>
  <div class="test-input">
      <div class="input">
        <div class="input-label">
          <p class="label-p">{{ label }}</p>
        </div>
        <form class="input-form">
          <input class="input-text" v-model=newValue @input="changeInput">
        </form>
      </div>
  </div>
</template>
<script>
export default {
  props: {
    label: {
      type: String,
      default: 'ID',
    },
    value: {
      type: String,
      default: 'Value 확인',
    },
  },
  computed: {
    newValue: {
      get() {
        return this.value;
      },
      set(val) {
        this.$emit('input', val);
      },
    },
  },
  methods: {
    changeInput(event) {
      this.$emit('input', event.target.value);
    }
  }
}
</script>
<style lang="css">
  .test-input {
    width: 300px;
    margin: 0 auto;
    text-align: left;
    padding-bottom: 10px;
  }
  .input {
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .input-label {
    width: calc(100% - 250px)
  }
  .input-form {
    width: 250px;
    text-align: right;
  }
  .input-text {
    height: 25px;
  }
  .label-p {
    margin: 0;
    padding-right: 10px;
  }
</style>
