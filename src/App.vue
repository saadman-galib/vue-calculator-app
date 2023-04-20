<template>
    <div>
        <div class="container">
            <Navbar />
            <Display />
            <div class="buttons-container">
                <Button
                    v-for="button in buttonList"
                    :key="button.index"
                    :button="button"
                />
            </div>
        </div>
    </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Display from "./components/Display.vue";
import Button from "./components/Button.vue";

export default {
    name: "App",
    data() {
        return {
            buttonList: [
                { index: 1, data: "7" },
                { index: 2, data: "8" },
                { index: 3, data: "9" },
                { index: 4, data: "DEL" },
                { index: 5, data: "4" },
                { index: 6, data: "5" },
                { index: 7, data: "6" },
                { index: 8, data: "+" },
                { index: 9, data: "1" },
                { index: 10, data: "2" },
                { index: 11, data: "3" },
                { index: 12, data: "-" },
                { index: 13, data: "." },
                { index: 14, data: "0" },
                { index: 15, data: "/" },
                { index: 16, data: "x" },
                { index: 17, data: "RESET" },
                { index: 18, data: "=" },
            ],
        };
    },
    components: {
        Navbar,
        Display,
        Button,
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

.buttons-container {
    display: flex;
    flex-wrap: wrap;
    flex-direction: row;
}
</style>
