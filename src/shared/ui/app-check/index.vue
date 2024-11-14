<template>
  <div
    class="inline-flex justify-start bg-[#DCDCDC] rounded-full w-8 h-4 p-[1px] cursor-pointer"
    :class="{ '!bg-[#316FEE] !justify-end': isChecked, '!w-12 !h-6': big }"
    @click="emits('onCheck')"
  >
    <div class="bg-white rounded-full w-[14px] h-[14px]" :class="{ '!w-[22px] !h-[22px]': big }" />
  </div>
</template>

<script setup lang="ts">
interface Props {
  isChecked: boolean
  big?: boolean
}

defineProps<Props>()

const emits = defineEmits<{
  (e: 'onCheck'): void
}>()
</script>
