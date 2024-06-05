<!-- time counter -->
<!-- <template>
    <div class="q-pa-md q-gutter-md row ">
      <q-btn color="teal" @click="decrement">
        <div>-</div>
      </q-btn>
      <q-input outlined v-model="text" label="Outlined" />
      <q-btn color="teal" @click="increment">
        <div>+</div>
      </q-btn>
    </div>
  </template>
  
  <script setup lang="ts">
  import { ref } from 'vue';
  
  const text = ref('0');
  
  const increment = (() => {
    text.value = (parseInt(text.value) + 1).toString();
  });
  
  const decrement = () => {
    text.value = (parseInt(text.value) - 1).toString();
  };
  </script> -->



  <!-- old code -->
  <!-- <template>
    <div>
      <TodoList :items="items" />
    </div>
    <div class="tw-fontWeight-bold tw-fontSize-xl tw-text-5xl tw-justify-center">jello</div>
  </template>
  
  <script setup lang="ts">
  import { ref } from 'vue';
  import TodoList from './TodoList.vue';
  
  const items = ref<string[]>([]);
  
  </script>
  
   -->


   <template>
    <div>
      <div v-for="(item, index) in items" :key="index">
        <TodoList :item="item" :index="index" @remove="removeItem" @update:item="updateItem(index, $event)" />
      </div>
      <AddList @add="addItem" />
      <!-- <div class="tw-fontWeight-bold tw-fontSize-xl tw-text-5xl tw-justify-center">jello</div> -->
    </div>
  </template>
  
  <script setup lang="ts">
  import { ref } from 'vue';
  import TodoList from './TodoList.vue';
  import AddList from './AddList.vue';
  
  const items = ref<string[]>([]);
  
  function addItem(item: string){
    items.value.push(item);
  };
  
  function removeItem(index: number){
    items.value.splice(index, 1);
  };
  
  function updateItem(index: number, newItem: string){
    items.value[index] = newItem;
  };
  </script>
  