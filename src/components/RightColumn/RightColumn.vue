<template>
  <div class="right-column__wrap">
    <p class="text">Используйте этот список, чтобы точно не допустить ошибок в подборе юриста, и он точно помог вам решить вашу проблему.</p>
    <div class="right-column__wrap__list">
      <check-box-list :list="list" />
    </div>
    <h1 class="title">Присоединяйтесь к раннему тестированию</h1>
    <form class="form">
      <v-input v-model="email" placeholder="E-mail" type="email" />
      <v-button @click="onButtonHandler()" :disabled="isDisable" type="submit">{{ btnText }} <Arrow v-if="!isDisable" /></v-button>
    </form>
  </div>
</template>

<script>
import CheckBoxList from '@/components/CheckBoxList/CheckBoxList.vue';
import VButton from '@/components/VButton.vue';
import Arrow from '@/assets/icons/arrow/Arrow.vue';
import VInput from '@/components/Vinput.vue';

export default {
  name: 'RightColumn',
  components: {VInput, Arrow, VButton, CheckBoxList},
  data() {
    return {
      list: [
        {
          id: 1,
          title: '1. Определите свои потребности',
          checks: [
            {
              id: 1,
              isChecked: false,
              label: 'Определите область права, в которой вам нужна помощь. Например, семейное право, уголовное право, налоговое право или другое.'
            },
            {
              id: 2,
              isChecked: false,
              label: 'Определите область права, в которой вам нужна помощь. Например, семейное право, уголовное право, налоговое право или другое.'
            },
          ]
        },
        {
          id: 2,
          title: '2. Поиск кандидатов',
          checks: [
            {
              id: 1,
              isChecked: false,
              label: 'Обратитесь к своим друзьям, близким родственникам и коллегам и попросите их дать вам рекомендации на основе их личного опыта.'
            },
            {
              id: 2,
              isChecked: false,
              label: 'Поищите онлайн-отзывы о юристах в вашем регионе. Сервисов много, но они не содержательны.'
            },
            {
              id: 3,
              isChecked: false,
              label: 'Попросите юриста предоставить ссылки на прошлых клиентов или свидетельства успешных дел.'
            },
          ]
        },
        {
          id: 3,
          title: '3. Проверьте квалификацию',
          checks: [
            {
              id: 1,
              isChecked: false,
              label: 'Убедитесь, что у юриста есть диплом о Высшем образовании и опыт работы. Сам университет не играет роли, важно где и кем работал кандидат.'
            },
            {
              id: 2,
              isChecked: false,
              label: 'Проверьте опыт и специализацию юриста в вашей области права: вдруг “опыт 15 лет” говорит не о юриспруденции, а о преподавании или о несвязанной госслужбе.'
            },
            {
              id: 3,
              isChecked: false,
              label: 'Учтите количество выигранных дел и специализацию. Один юрист не может быть хорош во всех вопросах.'
            },
            {
              id: 4,
              isChecked: false,
              label: 'Узнайте о репутации юриста и фирмы, которой он принадлежит. Не было ли случаев нарушения договора или же сотрудничества с вашими процессуальными оппонентами.'
            },
            {
              id: 5,
              isChecked: false,
              label: 'Проверьте наличие жалоб в отношении юриста. Для этого подойдут как и профессиональные ресурсы, так и социальные сети. Учтите что плохие комментарии могут быть удалены.'
            },
          ]
        },
        {
          id: 4,
          title: '4. Определите стоимость и гонорар',
          checks: [
            {
              id: 1,
              isChecked: false,
              label: 'Спросите о тарифах и методах оплаты: по часам, за проект, фиксированная ставка. Это важно знать до заключения договора об оказании юридических услуг, чтобы не столкнуться с нежеланными тратами.'
            },
            {
              id: 2,
              isChecked: false,
              label: 'Попросите детализированную оценку стоимости услуг. Часто содержание того же адвокатского договора может не включать важные для вас действия: выезд и сопровождение.'
            },
          ]
        },
        {
          id: 5,
          title: '5. Уделите внимание коммуникации',
          checks: [
            {
              id: 1,
              isChecked: false,
              label: 'Оцените, насколько хорошо юрист объясняет сложные юридические понятия. При этом важно чтобы вы понимали  не только содержание речи, но и договора.'
            },
            {
              id: 2,
              isChecked: false,
              label: 'Убедитесь, что у вас есть четкое понимание того, как будет осуществляться общение и взаимодействие в процессе работы. Отношения могут меняться, например, в зависимости от стадии процесса.'
            },
            {
              id: 3,
              isChecked: false,
              label: 'Оцените, насколько вы чувствуете себя комфортно и доверяете юристу. Учитывайте ваше интуитивное впечатление от встречи с юристом.'
            },
          ]
        },
        {
          id: 6,
          title: '6. Принимайте решение',
          checks: [
            {
              id: 1,
              isChecked: false,
              label: 'Сравните всех кандидатов и возьмите во внимание все аспекты, такие как опыт, репутация, стоимость и ваше взаимодействие с юристом. '
            },
            {
              id: 2,
              isChecked: false,
              label: 'Принимайте решение, основанное на балансе между качеством и ценой, а также на вашем личном чувстве уверенности в выборе.'
            },
          ]
        },
        {
          id: 7,
          title: '7. Или найдите юриста на сервисе InLaw',
          checks: [
            {
              id: 1,
              isChecked: false,
              label: 'Мы разрабатываем сервис поиска юристов на основе ИИ. Решим все проблемы поиска подходящего кандидата за Вас.'
            },
          ]
        },
      ],
      btnText: 'Присоединиться',
      isDisable: false,
      email: '',
    };
  },
  methods: {
    onButtonHandler() {
      this.btnText = 'Отправлено';
      this.isDisable = true;
    },
  },
};
</script>

<style scoped lang="scss">
.right-column__wrap {
  display: flex;
  flex-direction: column;
  gap: 60px;

  &__list {
    display: flex;
    flex-direction: column;
    gap: 100px;

    @media(max-width: 800px) {
      gap: 80px;
    }
  }
}

.form {
  display: flex;
  gap: 24px;

  @media(max-width: 800px) {
    flex-direction: column;
    gap: 12px;
  }

  input {
    width: 100%;
  }

  button {
    @media(max-width: 800px) {
      width: 100%;
      border-radius: 12px;
    }
  }
}
</style>