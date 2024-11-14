<template>
  <div>
    <AppHeader />
    <AppContainer>
      <div class="flex justify-center mt-7 md:mt-6">
        <BreadCrumbs />
      </div>
      <h1
        class="font-medium text-[32px]/[42px] mt-2 md:text-[56px]/[72px] text-[#000] md:mt-6 text-center mb-6"
      >
        Подписки «Клерка»
      </h1>
      <div class="flex justify-center">
        <AppTabs />
      </div>
    </AppContainer>
  </div>
</template>

<script lang="ts" setup>
import { AppContainer } from '@/shared/ui'
import { BreadCrumbs } from '@/widgets/bread-crumbs'
import { AppHeader } from '@/widgets/header'
import { AppTabs } from '@/widgets/tabs'
</script>
