<template>
    <div class="theme-toggle-container">
        <p>Theme</p>
        <div class="theme-toggle"><Theme /><Theme /><Theme /></div>
    </div>
</template>

<script>
import Theme from "./Theme.vue";

export default {
    name: "ThemeToggle",
    data() {
        return {
            // write your data here
        };
    },
    components: {
        Theme,
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
}
</style>
