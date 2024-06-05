<template>
    <div class="q-pa-md q-gutter-md row align-center justify-center">
        <q-input outlined v-model="newItem" label="Add Item" class="flex-1" />
        <q-btn square color="green" icon="check" @click="handleAddItem" />
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import { defineEmits } from 'vue';

const newItem = ref<string>('');
const emits = defineEmits<{
    (e: 'add', newItem: string): void
}>();

function handleAddItem() {
    if (newItem.value.trim() !== '') {
        emits('add', newItem.value.trim());
        newItem.value = '';
    }
};
</script>