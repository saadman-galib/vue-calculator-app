<template>
    <div class="nav-container">
        <div class="nav-left-part">
            <h2>calc</h2>
        </div>
        <div class="nav-right-part">
            <ThemeToggle />
        </div>
    </div>
</template>

<script>
import ThemeToggle from "./ThemeToggle.vue";

export default {
    name: "Navbar",
    data() {
        return {
            // write your data here
        };
    },
    components: {
        ThemeToggle
    },
    methods: {
        // write your methods here
    },
    computed: {
        // write your computed properties here
    },
    mounted() {
        // write your code here
    },
};
</script>

<style>
/* write your styles here */
.nav-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.nav-left-part h2{
    color: #fff;
    font-size: 32px;
    font-weight: 700;
}


</style>
