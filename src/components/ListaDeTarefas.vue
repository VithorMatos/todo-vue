<script setup>
    const props = defineProps(['tarefas']);

</script>

<template>
    <ul v-if="tarefas.length > 0 ">
        <ul class="list-group mt-4">
            <li class="list-group-item" v-for="tarefa in props.tarefas">
                <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada"
                    :id="tarefa.titulo" type="checkbox">
                <label :class="{ done: tarefa.finalizada }" class="ms-3" :for="tarefa.titulo">
                    {{ tarefa.titulo }}
                </label>
            </li>
        </ul>
    </ul>
    <span v-else>Nao existe tarefas pendentes</span>
</template>

<style scoped>
    .done{
        text-decoration: line-through;
    }
</style>