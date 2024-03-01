<script setup>
import { defineProps, defineEmits, ref, onMounted, onUnmounted } from 'vue';
const props = defineProps(['show']);
const emit = defineEmits(['close']);

let name = ref('');
let email = ref('');
let password = ref('');
let showSuccessModal = ref(false);

const closeSuccessModal = () => {
  showSuccessModal.value = false;
  document.body.removeEventListener('click', closeSuccessModal);

  name.value = '';
  email.value = '';
  password.value = '';
};
onMounted(() => {
  if (showSuccessModal.value) {
    document.body.addEventListener('click', closeSuccessModal);
  }
});

onUnmounted(() => {
  document.body.removeEventListener('click', closeSuccessModal);
});

const onSubmit = () => {
  showSuccessModal.value = true;
  document.body.addEventListener('click', closeSuccessModal);
  emit('close');
};
</script>

<template>
  <section class="registration" v-if="props.show">
    <div class="container">
      <div class="row justify-content-center">
        <div class="col-6">
          <div class="registration__text">
            <h2>Регистрация</h2>
            <p>Зарегистрируйтесь, чтобы получить доступ к личному кабинету</p>
          </div>
        </div>
        <div class="col-6">
          <form class="form" method="post" @submit.prevent="onSubmit">
            <label class="mb-3">
              <input type="text"
                     placeholder="Имя"
                     pattern="[A-Za-zА-Яа-яЁё]+"
                     title="Введите ваше имя"
                     v-model="name" required>
            </label>
            <label class="mb-3">
              <input type="email"
                     placeholder="Электронная почта"
                     title="Введите вашу электронную почту"
                     v-model="email" required>
            </label>
            <label class="mb-3">
              <input type="password"
                     placeholder="Пароль"
                     title="Введите ваш пароль"
                     v-model="password" required>
            </label>
            <button type="submit">Зарегистрироваться</button>
          </form>
        </div>
      </div>
    </div>
  </section>
  <div class="modal" v-show="showSuccessModal">
    <p>Регистрация успешно проведена, {{ name }}!</p>
  </div>
</template>

<style scoped lang="scss">
@import "src/assets/RegistrationModal.scss";
</style>