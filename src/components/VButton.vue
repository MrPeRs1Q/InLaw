<template>
  <button
      :class="{
         ['button']: true,
         [`button--${variant}`]: true,
      }"
      :type="type"
      @click="$emit('click')"
  >
    <slot/>
  </button>
</template>

<script>
export default {
  name: 'VButton',
  props: {
    variant: { type: String, default: 'filled' },
    type: { type: String, default: '' },
  },
};
</script>

<style scoped lang="scss">
.button {
  padding: 11px 12px;
  border-radius: 25px;
  font-family: 'Cera Pro', sans-serif;
  font-size: 16px;
  font-weight: 400;
  line-height: 20.8px;
  letter-spacing: -0.02em;
  cursor: pointer;
  display: flex;
  gap: 8px;
  align-items: center;
  justify-content: center;

  &--filled {
    background: var(--blue);
    color: var(--white);
  }

  &:disabled {
    opacity: 0.5;
  }
}
</style>