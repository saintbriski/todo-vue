<script setup>
    const props = defineProps(['tarefas']);
</script>

<template>
    <ul class="list-group mt-4">
        <li class="list-group-item custom-list-item-2" v-for="tarefa in props.tarefas">
            <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada"
                :id="tarefa.titulo" type="checkbox" />
            <label :class="{ done: tarefa.finalizada }" class="ms-3" :for="tarefa.titulo">
                {{ tarefa.titulo }}
            </label>
        </li>
        <li class="list-group-item custom-list-item" v-if="props.tarefas.filter(tarefa => !tarefa.finalizada).length === 0">
            Não existem tarefas pendentes
        </li>
    </ul>
</template>

<style scoped>
    .done {
        text-decoration: line-through;
    }
    .custom-list-item {
        background-color: #CCD0CF;
        border: 1px solid #ced4da;
        padding: 6px;
        margin-top: 25px;
        border-radius: 4px;
        color: #06141B;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 1rem;
        font-weight: 400;
        line-height: 1.5;
        transition: border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
    }
    .custom-list-item-2 {
    background-color: #CCD0CF; 
    border-color: #ced4da; 
    color: #06141B; 
}

.custom-list-item-2:hover {
    background-color: #CCD0CF; 
    border-color: #bdbdbd; 
    color: #06141B; 
}

.custom-list-item-2:focus {
    background-color: #CCD0CF; 
    color: #06141B; 
    outline: 0; 
    box-shadow: 0 0 0 0.2rem rgba(0, 123, 255, 0.25); 
}
</style>