<script setup>
import TaskComponent from '@/components/TaskComponent.vue'
import { ref } from 'vue';

const tareas = ref(['Estudiar', 'Sacar 5.0', 'Descansar'])

function deleteTasks(index) {
  //console.log('Borrar hijo', index)
  tareas.value.splice(index,1)
}

</script>

<template>
  <div class="bg-gray-50 w-96 shadow-md rounded mx-auto mt-12 px-4 py-3">
    <h1 class="text 2xl font-semibold">Tareas</h1>

    <div class="flex mt-2">
      <input class="rounded-r-none w-4/5 h-8 px-2 border rounded border-green-600" />
      <span
        class="hover:cursor-pointer hover:bg-green-700 text-center text-white rounded-l-none w-1/5 h-8 text-xl rounded bg-green-600">+
      </span>
    </div>

    <taskComponent
      v-for="(task,index) in tareas" 
      :key="index"
      :tarea="task"
      :index="index"
      @borrarTarea="deleteTasks"
    />

  </div>
</template>
