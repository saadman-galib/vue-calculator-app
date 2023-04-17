<template>
    <div
        class="theme"
        :style="{
            borderRadius: `${isStart()} ${isEnd()} ${isEnd()} ${isStart()}`,
        }"
    ></div>
</template>

<script>
export default {
    name: "App",
    data() {
        return {
            // write your data here
        };
    },
    props: {
        start: {
            type: Boolean,
            default: false,
        },
        end: {
            type: Boolean,
            default: false,
        },
    },
    methods: {
        // write your methods here
        isStart() {
            return this.start ? "50%" : "0%";
        },
        isEnd() {
            return this.end ? "50%" : "0%";
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
.theme {
    background: #fff;
    width: 22px;
    height: 22px;
    cursor: pointer;
}
</style>
