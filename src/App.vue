<template>
    <div>
        <div class="container">
            <Navbar />
            <Display />
            <div class="buttons-container"></div>
        </div>
    </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Display from "./components/Display.vue";

export default {
    name: "App",
    data() {
        return {};
    },
    components: {
        Navbar,
        Display,
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
    /*background: whitesmoke; */
    width: 550px;
    height: 700px;
    border-radius: 10px;
    padding: 8px;
}
</style>
