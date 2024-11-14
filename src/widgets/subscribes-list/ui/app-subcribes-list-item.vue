<template>
  <li class="px-4 md:px-6 py-6 rounded-xl hover:shadow-md bg-white">
    <div class="md:flex md:flex-col lg:flex-row items-start justify-between gap-6">
      <div>
        <div class="flex items-start justify-between">
          <div>
            <h4 class="text-[#999999] text-[13px]/[16px]">{{ item.subtitle }}</h4>
            <h3 class="font-medium text-xl mb-2">{{ item.title }}</h3>
          </div>
          <img class="w-10 h-10 block md:hidden" :src="item.icon" :alt="item.title" />
        </div>
        <p v-html="item.description" class="text-sm mb-4 text-[#666666]" />
        <ul class="mb-6 space-y-2">
          <li
            v-for="checkItem in item.checkList"
            :key="checkItem"
            class="flex items-baseline text-sm gap-2"
          >
            <img src="/icons/check.svg" alt="check" />
            <span v-html="checkItem" />
          </li>
        </ul>
        <div class="flex items-center gap-4">
          <AppCheck big :is-checked="isChecked" @on-check="toggleCheck" />
          <p class="text-sm">Уже получает {{ item.subscribers.toLocaleString('ru-RU') }} человек</p>
        </div>
      </div>
      <img class="hidden md:block w-20 h-20" :src="item.icon" :alt="item.title" />
    </div>
  </li>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import type { SubscribesItem } from '../model'
import { AppCheck } from '@/shared/ui'

interface Props {
  item: SubscribesItem
}

defineProps<Props>()

const isChecked = ref(false)

const toggleCheck = () => {
  isChecked.value = !isChecked.value
}
</script>
