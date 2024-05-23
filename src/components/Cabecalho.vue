<script setup>
    const props = defineProps(['tarefasPendentes'])
</script>
<template>
    <header class="p-5 mb-4 mt-4 rounded-3">
        <h1>Minhas tarefas</h1>
        <p>
            Você possui {{ props.tarefasPendentes }} tarefas pendentes
        </p>
    </header>
</template>

<style scoped>
    header {
        background-color: #4A566A;
    }
    h1, p {
        color: #CCD0CF;
    }
</style>