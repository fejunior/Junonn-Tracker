<template>
  <button class="button" @click="clicado" :disabled="desabilitado">
    <span class="icon">
      <i :class="'fas ' + icon"></i>
    </span>
    <span>{{ text }}</span>
  </button>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "Botao",
  emits: ["clicado"],
  props: {
    desabilitado: {
      type: Boolean,
    },
    text: {
      type: String,
      required: true,
    },
    icon: {
      type: String,
      required: true,
    },
  },
  methods: {
    clicado(): void {
      this.$emit("clicado");
    },
  },
});
</script>

