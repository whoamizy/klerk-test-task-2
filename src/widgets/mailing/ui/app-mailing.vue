<template>
  <div>
    <h2 class="font-medium text-2xl mb-4 md:text-center md:mb-6">
      Выберите рассылки, которые подходят именно вам
    </h2>
    <form @click.prevent="onSubmit" class="flex justify-between bg-white rounded-full">
      <input
        type="email"
        v-model="email"
        placeholder="Электронная почта"
        class="block grow outline-none text-base placeholder:text-[#666] p-4 rounded-l-[4px] md:rounded-l-lg"
      />
      <button class="bg-[#316FEE] p-4 rounded-full hover:opacity-70 md:px-8">
        <img class="block md:hidden" src="/icons/mailing-arrow.svg" alt="mailing-arrow" />
        <span class="hidden md:block text-base text-white">Подписаться</span>
      </button>
    </form>
    <div class="inline-flex items-center gap-2 mt-4">
      <AppCheck :is-checked="subscribeAll" @on-check="onSubscribeAll" />
      <p class="text-sm">Подписаться на все рассылки</p>
    </div>
  </div>
</template>

<script setup lang="ts">
import { AppCheck } from '@/shared/ui'
import { ref } from 'vue'

const email = ref('')
const subscribeAll = ref(false)

const emits = defineEmits<{
  (e: 'subscribe', email: string): void
}>()

const onSubmit = () => {
  emits('subscribe', email.value)
  email.value = ''
}

const onSubscribeAll = () => {
  subscribeAll.value = !subscribeAll.value
}
</script>
