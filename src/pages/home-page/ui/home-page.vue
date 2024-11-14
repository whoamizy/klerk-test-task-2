<template>
  <div>
    <AppHeader />
    <AppContainer>
      <div class="flex justify-center mt-7 md:mt-6">
        <BreadCrumbs />
      </div>
      <h1
        class="font-medium text-[32px]/[42px] mt-2 md:text-[56px]/[72px] md:mt-6 text-center mb-6"
      >
        Подписки «Клерка»
      </h1>
      <div class="flex justify-center">
        <AppTabs />
      </div>
      <div class="bg-[#F5F5F8] max-md:-mx-4 px-4 py-8 md:px-6 md:py-12 md:rounded-2xl">
        <div class="mb-6 md:px-6">
          <AppMailing @subscribe="subscribe" />
        </div>
        <AppSubscribesList />
      </div>
    </AppContainer>
    <AppFooter />
  </div>
</template>

<script lang="ts" setup>
import { AppContainer } from '@/shared/ui'
import { BreadCrumbs } from '@/widgets/bread-crumbs'
import { AppFooter } from '@/widgets/footer'
import { AppHeader } from '@/widgets/header'
import { AppMailing } from '@/widgets/mailing'
import { AppSubscribesList } from '@/widgets/subscribes-list'
import { AppTabs } from '@/widgets/tabs'

const subscribe = (email: string) => {
  console.log(email)
}
</script>
