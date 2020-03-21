<template>
  <div class="about">
    <h1>Título: {{ titulo }}</h1>
    <h2 v-for="(item, index) in tareasState" :key="index">{{ item }}</h2>
    <h3>Contador: {{ contador }}</h3>
    <button @click="aumentarContador(1)">Aumentar contador</button>
  </div>
</template>

<script>
import { mapState, mapMutations } from "vuex";

export default {
  computed: {
    ...mapState(['titulo']),
    ...mapState('tareas', ['tareasState']),
    ...mapState('contador', ['contador']),
  },
  methods: {
    ...mapMutations('contador', ['aumentarContador']),
  },
}
</script>
