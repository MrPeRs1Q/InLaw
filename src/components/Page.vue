<template>
  <div class="container">
    <div class="container__left-column">
      <left-column />
    </div>
    <div class="container__right-column">
      <right-column />
    </div>
  </div>
</template>

<script>
import LeftColumn from '@/components/LeftColumn/LeftColumn.vue';
import RightColumn from '@/components/RightColumn/RightColumn.vue';

export default {
  name: 'Page',
  components: { RightColumn, LeftColumn }
};
</script>

<style scoped lang="scss">
.container {
  width: 100%;
  height: 100%;
  display: flex;
  gap: 134px;
  max-width: 1440px;
  margin: 0 auto;
  padding: 60px 72px;

  @media(max-width: 800px) {
    flex-direction: column;
    gap: 24px;
    padding: 0 20px 20px 20px;
  }

  &__left-column {
    background-color: var(--white);
    z-index: 10;
    position: sticky;
    top: 60px;
    left: 0;
    max-width: 530px;
    width: 100%;
    height: 100%;

    @media(max-width: 800px) {
      top: 0;
      padding: 20px 0;
    }
  }

  &__right-column {
    max-width: 800px;
    width: 100%;
    height: 100%;
  }
}
</style>