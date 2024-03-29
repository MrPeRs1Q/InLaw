<template>
  <input
      v-model="internalValue"
      :class="{
        [$style['input-container']]: true,
      }"
      :type="type"
      :placeholder="placeholder"
  />
</template>

<script>
export default {
  name: 'VInput',
  props: {
    value: {type: String, default: ''},
    type: {type: String, default: 'text'},
    placeholder: {type: String, default: ''},
  },
  data() {
    return {
      internalValue: this.value,
    };
  }
};
</script>

<style lang="scss" module>
.input-container {
  background: var(--lightBlue);
  border: none;
  border-radius: 12px;
  padding: 12px 11px;
  outline: none;
  color: var(--darkBlue);
  font-family: 'Cera Pro', sans-serif;
  font-size: 16px;
  font-weight: 400;
  line-height: 20.8px;
  letter-spacing: -0.02em;

  &:hover {
    border: 1px solid var(--blue);
  }

  &::placeholder {
    color: var(--darkBlue);
    opacity: 0.5;
  }
}
</style>
