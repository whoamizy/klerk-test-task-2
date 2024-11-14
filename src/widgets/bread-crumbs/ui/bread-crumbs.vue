<template>
  <nav>
    <ul class="flex">
      <BreadCrumbsItem v-for="(item, idx) in items" :key="idx" :crumb="item" :index="idx" />
    </ul>
  </nav>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import type { Crumb } from '../model'
import BreadCrumbsItem from './bread-crumbs-item.vue'

const items = ref<Crumb[]>([
  {
    text: 'Главная',
    path: '/',
  },
  {
    text: 'Рассылки',
    path: '/',
  },
  {
    text: 'Хлебные крошки',
    path: '/',
  },
])
</script>
