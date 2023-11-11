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
     
        isStart() {
            return this.start ? "50%" : "0%";
        },
        isEnd() {
            return this.end ? "50%" : "0%";
        },
        
    },
   
};
</script>

<style>
.theme {
    background: #fff;
    width: 22px;
    height: 22px;
    cursor: pointer;
}
</style>
