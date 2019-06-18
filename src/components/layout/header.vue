<template>
    <header class="header">
        <h3>Vue To Do List</h3>
        <div id="nav">
            <router-link to="/">Todos</router-link> |
            <router-link to="/about">About</router-link>
        </div>
    </header>
</template>

<script>
export default {
    name: "Header"
}
</script>

<style scoped>
    .header{
        flex: 100;
        background: #353535;
        color: #fff;
        text-align: center;
        padding: 10px;
    }
    .header a{
        color: #fff;
        padding-right: 5px;
    }
    .header h3{
        font-weight: 200;
    }
    #nav{
        padding-top: 10px;
    }
</style>
