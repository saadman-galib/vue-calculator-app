<template>
    <div class="display-container">
        <p>{{ changeValue() }}</p>
    </div>
</template>

<script>
export default {
    name: "App",
    data() {
        return {
            value: this.display,
        };
    },
    props: {
        display: {
            required: true,
        },
    },
    methods: {
        changeValue() {
            this.value = this.display;

            // if (this.value > 999) {
            //     let commas = this.value.toLocaleString("en-US");
            //     return commas;
            // } else {
            //     return this.value;
            // }
            return this.value;
        },
    },
};
</script>

<style>
.display-container {
    background: var(--display-bg);
    min-width: 100%;
    height: 100%;
    max-height: 130px;
    border-radius: 10px;
    padding: 8px;
    margin: 30px auto;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    padding: 32px;
    transition: 0.7s;
}

.display-container p {
    color: var(--display-text-color);
    font-size: 60px;
    font-weight: 700;
    transition: 0.7s;
    height: 45px;
}

@media (max-width: 645px) {
    .display-container p {
        font-size: 40px;
        height: 30px;
    }
}
</style>
