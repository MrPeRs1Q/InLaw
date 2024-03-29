<template>
  <div v-for="(value, index) in list" :key="index" class="list-container">
    <p class="title">{{ value.title }}:</p>
    <div v-for="(it, id) in value.checks" class="list-container__checkbox" :key="id">
      <Transition><img v-if="!it.isChecked" src="@/assets/icons/checkbox/checkbox-false.png" alt="true" @click="it.isChecked = !it.isChecked"></Transition>
      <Transition><img v-if="it.isChecked" src="@/assets/icons/checkbox/checkbox-true.png" alt="true" @click="it.isChecked = !it.isChecked"></Transition>
      <span class="text" @click="it.isChecked = !it.isChecked">{{ it.label }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CheckBoxList',
  props: {
    list: { type: Array, default: () => [] },
  },
};
</script>

<style scoped lang="scss">
.list-container {
  display: flex;
  flex-direction: column;
  gap: 40px;

  &__checkbox {
    display: flex;
    gap: 24px;
    align-items: center;
    cursor: pointer;
  }
}
</style>