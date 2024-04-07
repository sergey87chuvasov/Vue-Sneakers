<script setup>
import DrawerHead from './DrawerHead.vue'
import CartItemList from './CartItemList.vue'

const emit = defineEmits(['createOrder'])

defineProps({
  totalPrice: Number,
  vatPrice: Number,
  buttonDisabled: Boolean
})
</script>

<template>
  <div class="fixed top-0 left-0 h-full w-full bg-black z-10 opacity-70">
    <div class="bg-white w-96 h-full fixed right-0 top-0 z-20 p-8">
      <DrawerHead />

      <CartItemList />

      <div class="flex flex-col gap-4 mt-7">
        <div class="flex gap-2">
          <span>Итого:</span>
          <div class="flex-1 border-b border-dashed"></div>
          <b>{{ totalPrice }} BYN</b>
        </div>

        <div class="flex gap-2">
          <span>Налог 5%:</span>
          <div class="flex-1 border-b border-dashed"></div>
          <b>{{ vatPrice }} BYN</b>
        </div>

        <button
          :disabled="buttonDisabled"
          @click="() => emit('createOrder')"
          class="bg-lime-500 mt-4 w-full rounded-xl py-3 text-white disabled:bg-slate-300 hover:bg-lime-600 transition active:bg-lime-700 cursor-pointer"
        >
          Оформить заказ
        </button>
      </div>
    </div>
  </div>
</template>
