<template>
    <div class="theme-toggle-container">
        <p>Theme</p>
        <div class="theme-toggle">
            <Theme start="true" @click="changePosition(0)" />
            <Theme @click="changePosition(1)" />
            <Theme end="true" @click="changePosition(2)" />
            <div class="theme-toggle-ball" :style="{ left: leftPos }"></div>
        </div>
    </div>
</template>

<script>
import Theme from "./Theme.vue";

export default {
    name: "ThemeToggle",
    data() {
        return {
            // write your data here
            leftPos: 4,
        };
    },
    components: {
        Theme,
    },
    methods: {
        // write your methods here
        changePosition(index) {
            this.leftPos = 20 * index + 4 + index + "px";
        },
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
.theme-toggle-container {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    text-transform: uppercase;
}

.theme-toggle-container p {
    color: #fff;
    font-size: 12px;
    font-weight: 700;
    margin-top: auto;
    margin-bottom: auto;
    margin-right: 28px;
}

.theme-toggle {
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
}

.theme-toggle-ball {
    width: 16px;
    height: 16px;
    border-radius: 50%;
    background-color: red;
    position: absolute;
    cursor: pointer;
    transition: 0.2s;
}
</style>
