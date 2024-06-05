<!-- <template>
    <div>
      <div v-if="showInput" class="q-pa-md q-gutter-md row absolute-center">
        <q-input outlined v-model="txt" label="" />
        <q-btn square color="deep-orange" icon="close" @click="hideinput" />
      </div>
    </div>
</template>
  
  <script setup lang="ts">
  import { ref } from 'vue';
  
  const txt = ref<string>('');
  const showInput = ref(true);
  
 function hideinput(){
    showInput.value = false;
  };
  </script>
   -->
<!-- 
   <template>
    <div>
      <ul>
        <li v-for="(item, index) in items" :key="index">
          {{ item }}
        </li>
      </ul>
    </div>
  </template>
  
  <script setup lang="ts">
  import { defineProps } from 'vue';
  
  const props = defineProps({
    items: {
      type: Array as () => string[],
      required: true,
    },
  });
  </script>
   -->