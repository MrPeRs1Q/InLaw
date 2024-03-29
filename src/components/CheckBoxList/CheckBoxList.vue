<template>
  <div v-for="(value, index) in list" :key="index" class="list-container">
    <p class="title">{{ value.title }}:</p>
    <div v-for="(it, id) in value.checks" class="list-container__checkboxes" :key="id">
      <div class="list-container__checkboxes__checkbox">
        <input v-model="it.isChecked" type="checkbox">
        <label class="text">{{ it.label }}</label>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CheckBoxList',
  props: {
    list: { type: Array, default: () => [] },
  }
};
</script>

<style scoped lang="scss">
.list-container {
  display: flex;
  flex-direction: column;
  gap: 40px;

  &__checkboxes {
    display: flex;
    flex-direction: column;
    gap: 40px;

    &__checkbox {
      display: flex;
      gap: 24px;

      @media(max-width: 800px) {
        gap: 13px;
      }
    }
  }
}
</style>