<template>
    <header>
        <div id="nav">
            <router-link to="/">Home</router-link> |
            <router-link :to="{name : 'About'}">About</router-link> |
            <router-link to="/setting">Setting</router-link> 
        </div>
    </header>
</template>

<script>
export default {
    name:'Header'
}
</script>

<style scoped>
header{
    background: #222;
}
</style>



