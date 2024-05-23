<script setup>
const props = defineProps(['cadastraTarefa', 'tarefaTemp', 'trocarFiltro', 'editaTarefaTemp'])
</script>

<template>
    <form @submit.prevent="props.cadastraTarefa">
        <div class="row">
            <div class="col">
                <input :value="props.tarefaTemp" @change="props.editaTarefaTemp" required
                    type="text" placeholder="Digite aqui a descrição da tarefa" class="custom-input" />
            </div>
            <div class="col-md-2">
                <button type="submit" class="btn custom-btn">Cadastrar</button>
            </div>
            <div class="col-md-2">
                <select @change="props.trocarFiltro" class="custom-input">
                    <option value="todas">Todas as tarefas</option>
                    <option value="finalizadas">Finalizadas</option>
                    <option value="pendentes">Pendentes</option>
                </select>
            </div>
        </div>
    </form>
</template>

<style scoped>
    .custom-btn {
        display: inline-block;
        font-weight: 400;
        color: #ced4da;
        text-align: center;
        vertical-align: middle;
        user-select: none;
        background-color: #4A566A;
        border: 1px solid #4A566A;
        padding: 0.375rem 0.75rem;
        font-size: 1rem;
        line-height: 1.5;
        border-radius: 0.25rem;
        transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out, border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
        cursor: pointer;
    }
    .custom-btn:hover {
        color: #fff;
        background-color: #4A566A;
    }
    .custom-btn:focus {
        color: #fff;
        background-color: #4A566A;
        outline: 0;
        box-shadow: 0 0 0 0.2rem rgba(74, 86, 106, 1);
    }
    .custom-btn:active {
        color: #fff;
        background-color: #4A566A;
        border-color: #4A566A;
        box-shadow: 0 0 0 0.2rem rgba(74, 86, 106, 1);
    }
    .custom-btn:disabled {
        opacity: 0.65;
        cursor: not-allowed;
    }
    .custom-input {
        display: block;
        width: 100%;
        padding: 0.375rem 0.75rem;
        font-size: 1rem;
        font-weight: 400;
        line-height: 1.5;
        color: #06141B;
        border: 1px solid #ced4da;
        border-radius: 0.25rem;
        background-clip: padding-box;
        transition: border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
        background-color: #CCD0CF;
    }
    .custom-input:focus {
        color: #495057;
        background-color: #CCD0CF;
        border-color: #4A566A;
        outline: 0;
        box-shadow: 0 0 0 0.2rem rgba(74, 86, 106, 1);
    }
</style>