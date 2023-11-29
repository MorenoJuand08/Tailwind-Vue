<script setup>
const props = defineProps({
    tarea: {
        type: String,
        default: 'tarea indefinida'
    },

    index: {
        type: Number,
        }
})

const emit = defineEmits(['borrarTarea'])

function borrarTarea(index) {
    //console.log('Borrar Tarea', index)
    emit('borrarTarea', index)
}
</script>

<template>
  <div class="flex mt-2 justify-between bg-gray-200 rounded px-4 py-1">
    {{ props.tarea }}
    <span
      class="px-2 hover:cursor-pointer hover:bg-red-600 text-center text-white rounded bg-red-400" @click="borrarTarea(props.index)" >
      X
    </span>
  </div>
</template>
