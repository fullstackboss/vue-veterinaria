<script setup>
import { computed } from "vue";

const props = defineProps({
  valerta: {
    type: Object,
    required: true,
  },
});
const isError = computed(() => {
  return props.valerta.tipo === "error";
});
</script>
<template>
  <div
    :class="[isError ? 'bg-red-500' : 'bg-green-500']"
    class="text-white text-center p-3 uppercase font-bold mb-3 rounded-md"
  >
    {{ valerta.mensaje }}
  </div>
</template>
