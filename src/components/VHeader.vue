<script setup>
import { ref } from 'vue';
import RegistrationModal from './RegistrationModal.vue';

let showModal = ref(false);

const toggleModal = () => {
  showModal.value = !showModal.value;
};

const closeModal = () => {
  showModal.value = false;
};
</script>

<template>
  <header>
    <nav class="navigation">
      <div class="container">
        <div class="navigation__wrapp">
          <img src="/logo.svg" alt="logo">
          <ul class="navigation__list">
            <li class="navigation__list-item"><a href="#" class="navigation__list-link">Продукция</a></li>
            <li class="navigation__list-item"><a href="#" class="navigation__list-link">Материалы</a></li>
            <li class="navigation__list-item"><a href="#" class="navigation__list-link">О нас</a></li>
            <li class="navigation__list-item"><a href="#" class="navigation__list-link">Контакты</a></li>
            <li class="navigation__list-box">
              <a href="#" class="navigation__list-box-search">
                <img src="/Search.svg" alt="search">
              </a>
              <a href="#" class="navigation__list-box-login" @click.prevent="toggleModal">
                <img src="/log_in.svg" alt="login">
              </a>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </header>
  <RegistrationModal :show="showModal" @close="closeModal" />
</template>

<style scoped>

</style>