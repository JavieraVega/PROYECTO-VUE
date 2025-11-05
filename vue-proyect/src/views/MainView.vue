<template>
    <div class="container">
        <Sidebar />
        <div class="content">
            <router-view></router-view> <!--esta va a mostrar el contenido de una vista que se ha iniciado con un router link-->

        </div>

    </div>

</template>

<script setup>
import Sidebar from '@/components/Sidebar.vue';

</script>

<style>
.container {
    display: flex;
}
.content {
    flex: 1;
    padding: 20px;
}
</style>