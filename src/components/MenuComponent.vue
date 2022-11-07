<template>
    <nav>
        <ul id="menu">
            <li>
                <router-link to="/">Home</router-link> | 
            </li>
            <li>
                <router-link to="/doble/77">Doble 77</router-link> | 
            </li>
            <li>
                <router-link to="/doble/7">Doble 7</router-link> | 
            </li>
            <li>
                <router-link to="/doble/66">Doble 66</router-link> | 
            </li>            
            <li>
                <router-link to="/doble"> Doble sin número</router-link> | 
            </li>
            <li>
                <router-link to="/deportes/14">Deportes</router-link> | 
            </li>
            <li>
                <router-link to="/comics">Comics</router-link> | 
            </li>
        </ul>
    </nav>
</template>

<script>
    export default {
        name: "MenuComponent"
    }
</script>

<style>
    #menu li {
        display: inline
    }
</style>