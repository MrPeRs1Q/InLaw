<template>
  <div class="left-column__wrap">
    <Logo56 v-if="windowSizeForMobile <= 800"/>
    <div class="left-column__wrap__top">
      <h1 class="title">Как выбрать лучшего юриста?</h1>
      <p v-if="windowSizeForMobile > 800" class="text">Вот вам несколько советов по подбору подходящего специалиста</p>
    </div>
    <Logo140 v-if="windowSizeForMobile > 800" />
  </div>
</template>

<script>
import Logo140 from '@/assets/icons/logos/logo140/Logo140.vue';
import Logo56 from '@/assets/icons/logos/logo56/Logo56.vue';

export default {
  name: 'LeftColumn',
  components: {Logo56, Logo140 },
  data() {
    return {
      windowSizeForMobile: document.documentElement.clientWidth,
    }
  },
  mounted() {
    window.addEventListener("resize", this.isMobileHandler);
    this.isMobileHandler();
  },
  destroyed() {
    window.removeEventListener("resize", this.isMobileHandler);
  },
  methods: {
    isMobileHandler() {
      this.windowSizeForMobile = document.documentElement.clientWidth;
    }
  }
};
</script>

<style scoped lang="scss">
.left-column__wrap {
  display: flex;
  flex-direction: column;
  gap: 402px;

  @media(max-height: 800px) {
    gap: 150px;
  }

  @media(max-width: 800px) {
    flex-direction: row;
    gap: 10px;
  }

  &__top {
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 40px ;
  }
}
</style>