<template>
    <button
        class="button"
        :class="buttonType"
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
                data: "7",
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
        buttonType() {
            return this.button.data == "RESET" || this.button.data == "DEL"
                ? "btn-reset"
                : this.button.data == "="
                ? "btn-equal"
                : "";
        },
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
    background: var(--normal-btn-color);
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 12px;
    box-shadow: 0 5px 0 0 var(--normal-btn-shadow);
    margin: 8px;
    cursor: pointer;
    outline: none;
    border: none;
    transition: 0.7s;
}

.button:hover {
    background: var(--normal-btn-hover);
}

/* .button:focus{
    box-shadow: 0 4px 0 0 var(----normal-btn-shadow);
} */

.button p {
    color: var(--text-color);
    font-weight: 700;
    transform: translateY(3px);
    transition: 0.7s;
}

.btn-reset {
    background: var(--reset-btn-color);
    box-shadow: 0 5px 0 0 var(--reset-btn-shadow);
}

.btn-reset:hover {
    background: var(--reset-btn-hover);
}

.btn-reset p,
.btn-equal p {
    color: var(--reset-btn-text-color);
}

.btn-equal {
    background: var(--equal-btn-color);
    box-shadow: 0 5px 0 0 var(--equal-btn-shadow);
}

.btn-equal:hover {
    background: var(--equal-btn-hover);
}
</style>
