<template>
    <button
        class="button"
        :style="{ 'grid-column': changeWidth() }"
        @click="handleClick()"
    >
        <p :style="{ 'font-size': changeFontSize() }">{{ button.data }}</p>
    </button>
</template>

<script>
export default {
    name: "App",
    data() {
        return {};
    },
    props: {
        button: {
            type: Object,
            default: {
                index: 1,
                data: "0",
            },
        },
    },
    methods: {
        changeWidth() {
            if (this.button.data == "RESET" || this.button.data == "=") {
                return "span 2";
            } else {
                return "span 1";
            }
        },
        changeFontSize() {
            if (this.button.data.length > 1) {
                return "30px";
            } else {
                return "40px";
            }
        },
        handleClick() {
            this.$emit("handleClick", this.button.data);
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
.button {
    /*min-width: 110px; */
    /*min-height: 70px; */
    /* width: 87.3%;
    height: 81.4%; */
    min-width: 100%;
    min-height: 100%;
    background: #e6e5da;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 12px;
    box-shadow: 0 5px 0 0 #b4a398;
    margin: 8px;
    cursor: pointer;
    outline: none;
    border: none;
}

.button:focus{
    box-shadow: 0 4px 0 0 #b4a398;
}

.button p {
    color: #41485a;
    font-weight: 700;
    transform: translateY(3px);
}
</style>
