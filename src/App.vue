<script setup>
  import {
    useCounterStore
  } from './stores/counter'
  const items = useCounterStore()
</script>

<template>
  <main class="w-full h-screen p-[20px]">

    <div class="w-full h-full flex flex-col gap-[20px]">

      <div class="flex justify-between gap-[50px]">

        <div class="w-full border border-black p-[10px]">
          <ul class="flex flex-wrap gap-5">
            <li class="w-[100px] h-[100px] border-[2px] border-black cursor-pointer grid place-items-center"
              v-for="(item, index) in items.useritembag" :key="index" @click="items.deleteItem(index)">{{item.name}}
            </li>
          </ul>
        </div>

        <div class="w-full h-[200px] border border-black p-[10px] flex items-center justify-center">
            {{items.chooseitembag}}
        </div>
      </div>

      <div class="flex h-full gap-[50px]">
        <div class="w-full h-full border-[2px] border-black p-[10px]">
          <ul class="flex flex-wrap gap-5">
            <li class="w-[100px] h-[100px] border-[2px] border-black grid place-items-center cursor-pointer"
              v-for="(item, index) in items.useritem" :key="index" @click='items.AddItem(item)'>
              {{item.name}}
            </li>
          </ul>
        </div>

        <div class="w-full h-full border-[2px] border-black p-[10px]">
          <ul class="flex flex-wrap gap-5">
            <li class="w-[100px] h-[100px] border-[2px] border-black grid place-items-center cursor-pointer"
              v-for="(item, index) in items.chooseitem" :key="index"
              @click='items.ShowItem(item.name)'>{{item.name}}</li>
          </ul>
        </div>
      </div>


    </div>
  </main>
</template>

<style scoped>

</style>