<script setup lang="ts">
import { ref, computed } from 'vue'

interface Item {
  name: string
  completed: boolean
}

const items = ref<Item[]>([
  { name: 'たまご', completed: false},
  { name: 'りんご', completed: true }
])

const completedItems = computed(() => items.value.filter(item => item.completed))
const uncompletedItems = computed(() => items.value.filter(item => !item.completed))

const newItemName = ref('')

const addItem = () => {
  items.value.push({ name: newItemName.value, completed: false})
}
const completedItem = (item: Item, state: boolean) => {
  item.completed = state
}



</script>

<template>
  <div>
    
    <div>Uncompleted List</div>
    <ul>
      <li v-for="item in uncompletedItems" :key="item.name" >
        <div >
          名前: {{ item.name }}
          <button @click="completedItem(item, true)">Complete</button>
        </div>
      </li>
    </ul>
    
    <div>
      <label>
        名前
        <input v-model="newItemName" type="text" />
      </label>
      <button @click="addItem">add</button>
    </div>
    
    <div>Completed List</div>
    <ul>
      <li v-for="item in completedItems" :key="item.name">
        <div>
          名前: {{ item.name }}
          <button @click="completedItem(item, false)">Uncomplete</button>
        </div>
      </li>
    </ul>

  </div>
</template>

<style></style>