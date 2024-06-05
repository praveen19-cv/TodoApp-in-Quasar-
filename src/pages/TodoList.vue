<!-- 
 <template>
  <div>
    <div v-for="(item, index) in items" :key="index" class="q-pa-md q-gutter-md row align-center justify-center">
      <q-input outlined v-model="items[index]" class="flex-1" />
      <q-btn square color="red" icon="close" @click="removeItem(index)" />
    </div>
    <div class="q-pa-md q-gutter-md row align-center justify-center ">
      <q-input outlined v-model="newItem" label="Add Item" class="flex-1" />
      <q-btn square color="green" icon="check" @click="addItem" />
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const items = ref<string[]>([]);
const newItem = ref<string>('');

const addItem = () => {
  if (newItem.value.trim() !== '') {
    items.value.push(newItem.value.trim());
    newItem.value = '';
  }
};

const removeItem = (index: number) => {
  items.value.splice(index, 1);
};
</script> -->
<template>
  <div class="q-pa-md q-gutter-md row align-center justify-center">
    <q-input outlined :modelValue="item" @update:modelValue="updateItem" class="flex-1" />
    <q-btn square color="red" icon="close" @click="removeItem" />
  </div>
</template>

<script setup lang="ts">
import { defineProps, defineEmits } from 'vue';

const props = defineProps<{
  item: string,
  index: number
}>();

const emits = defineEmits<{
  (e: 'remove', index: number): void,
  (e: 'update:item', newItem: string): void
}>();

function updateItem(newItem: string | number | null){
  if (typeof newItem === 'string') {
    emits('update:item', newItem);
  }
};

function removeItem() {
  emits('remove', props.index);
};
</script>
