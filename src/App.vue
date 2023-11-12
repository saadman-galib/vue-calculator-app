<template>
    <div class="container">
        <Navbar />
        <Display :display="this.display" />
        <div class="buttons-container">
            <Button
                v-for="button in buttonList"
                :key="button.index"
                :button="button"
                @handleClick="calc"
            />
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
            display: "0",
        };
    },
    components: {
        Navbar,
        Display,
        Button,
    },
    methods: {
        calc(button) {
            switch (button) {
                case "+":
                case "-":
                case "x":
                case "/":
                    if (
                        this.display.slice(-1) === "+" ||
                        this.display.slice(-1) === "-" ||
                        this.display.slice(-1) === "x" ||
                        this.display.slice(-1) === "/"
                    ) {
                        this.display = this.display.slice(0, -1) + button;
                    } else {
                        this.display += button;
                    }
                    break;
                case "DEL":
                    this.display = this.deleteLastChar;
                    break;
                case "RESET":
                    this.display = "0";
                    break;
                case "=":
                    this.display = this.convertCrossToMultiplication;
                    this.display = eval(this.display).toString();
                    break;
                default:
                    if (this.display === "0") {
                        this.display = button;
                    } else {
                        this.display += button;
                    }
            }
        },
    },
    computed: {
        deleteLastChar() {
            if (this.display.length === 1) {
                return "0";
            }
            return this.display.slice(0, -1);
        },
        convertCrossToMultiplication() {
            return this.display.replace("x", "*");
        },
    },
};
</script>
<style>
.container {
    width: 600px;
    height: 750px;
    border-radius: 10px;
    padding: 8px;
}

.buttons-container {
    background: var(--btn-container-bg);
    border-radius: 12px;
    padding: 30px 25px 50px 25px;
    height: 520px;
    display: grid;
    grid-template-rows: repeat(5, 1fr);
    grid-template-columns: repeat(4, 108px);
    grid-gap: 28px;
    transition: 0.7s;
}

@media (max-width: 645px) {
    .container{
        width: 340px;
        height: auto;
        margin: 25px auto;
        
        
    }
    .buttons-container{
        height: 400px;
        padding: 15px 12.5px 35px 12.5px;
        grid-gap: 14px;
        grid-template-columns: repeat(4, 60px);

    }
}
</style>
