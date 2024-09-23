<template>
    <div class="sort-buttons">
        <button @click="sortByAsc">Сортировка по возрастанию</button>
        <button @click="sortByDesc">Сортировка по убыванию</button>
        <button @click="clearSort">Без сортировки</button>
    </div>
</template>
  
<script setup>
const emit = defineEmits(['sort', 'clear']);

function sortByAsc() {
  emit('sort', 'asc');
}

function sortByDesc() {
  emit('sort', 'desc');
}

function clearSort() {
  emit('sort', 'clear');
}
</script>
<style scoped>
  .sort-buttons {
    display: flex;
    justify-content: space-between;
    margin-bottom: 15px;
    width: 100%;
    gap: 5px;
  }

  .sort-buttons button {
    padding: 5px 10px;
    background-color: #fff;
    border: 1px solid #ccc;
    cursor: pointer;
    border-radius: 10px; 
    font-family: sans-serif;
    transition: background-color 0.3s, border-color 0.3s;    
  }

  .sort-buttons button:hover {
    background-color: #f0f0f0; 
    border-color: #888; 
  }

  .sort-buttons button:focus {
    outline: none; 
    box-shadow: 0 0 5px rgba(0, 123, 255, 0.5); 
  }
</style>