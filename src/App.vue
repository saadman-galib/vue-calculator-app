<template>
    <div>
        <div class="container">
            <Navbar />
        </div>
    </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";

export default {
    name: "App",
    data() {
        return {};
    },
    components: {
        Navbar: Navbar,
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
.container {
    background: #6f6c6c;
    width: 550px;
    height: 700px;
    border-radius: 10px;
}
</style>
