<template>
  <ul class="grid grid-cols-1 md:grid-cols-2 gap-6">
    <AppSubcribesListItem v-for="item in subscribes" :key="item.title" :item="item" />
  </ul>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import type { SubscribesItem } from '../model'
import AppSubcribesListItem from './app-subcribes-list-item.vue'

const subscribes = ref<SubscribesItem[]>([
  {
    subtitle: 'Перед рассветом',
    title: 'Утренний бухгалтер',
    description: 'Самые важные новости и события за день. <br/> Кратко, по делу, структурировано.',
    checkList: ['Новости для бухгалтеров, ИП и директора', 'Подборка статей за день'],
    icon: '/subscribes/1.png',
    subscribers: 59_342,
  },
  {
    subtitle: 'После заката',
    title: 'Ночной бухгалтер',
    description:
      'Самая краткая газета о налогах и бухучете в мире — современная рассылка для вечернего чтения.',
    checkList: ['Новости для бухгалтеров, ИП и директора', 'Подборка статей за день'],
    icon: '/subscribes/2.png',
    subscribers: 59_342,
  },
  {
    subtitle: 'Раз в две недели',
    title: 'Ножницы скидок',
    description: 'Подборка самых выгодных и полезных спецпредложений от надежных компаний.',
    checkList: ['Акции и скидки от лидеров рынка', 'Те, кто подписался – экономят много денег 🤑'],
    icon: '/subscribes/3.png',
    subscribers: 59_342,
  },
  {
    subtitle: 'По мере появления анонсов',
    title: 'Чемодан вебинаров',
    description:
      'Подборка с анонсами бесплатных вебинаров на самые топовые темы при участии экспертов.',
    checkList: ['<b>Никогда не пришлем платные вебинары</b>', 'Подборка топовых тем для вебинаров'],
    icon: '/subscribes/4.png',
    subscribers: 92_082,
  },
])
</script>
