<script setup>
import { ref } from "vue";

const name = ref("");
const link = ref("");
const description = ref("");
const freight = ref("");
const isVisible = ref(false);

const send = () => {
  isVisible.value = true;
};
</script>

<template>
  <div
    style="background-color: black; color: white"
    class="min-h-screen flex items-center justify-center"
  >
    <div
      class="w-10/12 p-4 text-center bg-white border border-gray-200 rounded-lg shadow sm:p-8 dark:bg-gray-800 dark:border-gray-700"
    >
      <h5 class="mb-2 text-3xl font-bold text-gray-900 dark:text-white">
        Gerador de postes
      </h5>
      <p class="mb-5 text-base text-gray-500 sm:text-lg dark:text-gray-400">
        Gere aqui seu postes para seus anúncios
      </p>
      <div
        class="items-center justify-center space-y-4 my-2 sm:flex sm:space-y-0 sm:space-x-4"
      >
        <div
          class="w-10/12 p-4 bg-white border border-gray-200 rounded-lg shadow sm:p-8 dark:bg-gray-800 dark:border-gray-700"
        >
          <form @submit.prevent="send">
            <div class="grid md:grid-cols-3 md:gap-4">
              <div class="relative z-0 w-full mb-6 group">
                <input
                  v-model="name"
                  type="text"
                  name="floating_first_name"
                  id="name"
                  class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                  placeholder="Nome"
                  required
                />
              </div>
              <div class="relative z-0 w-full mb-6 group">
                <input
                  v-model="link"
                  type="text"
                  name="floating_last_name"
                  id="Link"
                  class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                  placeholder="Link"
                  required
                />
              </div>
              <div class="relative z-0 w-full mb-6 group">
                <input
                  v-model="freight"
                  type="text"
                  name="floating_last_name"
                  id="frete"
                  class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                  placeholder="Frete"
                  required
                />
              </div>
            </div>
            <div class="grid md:grid-cols">
              <div class="relative z-0 w-full mb-6 group">
                <textarea
                  v-model="description"
                  type="text"
                  name="floating_first_name"
                  id="name"
                  class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                  placeholder="Descrição"
                  required
                ></textarea>
              </div>
            </div>
            <button
              type="button"
              @click="send"
              class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm w-full sm:w-auto px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800"
            >
              Gerar
            </button>
          </form>
        </div>
      </div>
      <div
        v-if="isVisible"
        class="items-center justify-center space-y-4 sm:flex sm:space-y-0 sm:space-x-4"
      >
        <div
          class="w-10/12 p-4 text-center bg-white border border-gray-200 rounded-lg shadow sm:p-8 dark:bg-gray-800 dark:border-gray-700"
        >
          <h5 class="mb-2 text-3xl font-bold text-gray-900 dark:text-white">
            Resultado
          </h5>
          <div>
            <p>📢{{ name }}</p>

            <p>➡De:</p>
            <p>{{ description }}</p>

            <p>🚚 {{ freight }}</p>

            <p>🛒 Compre com o link 👇🏾</p>

            <p>{{ link }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
