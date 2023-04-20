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
            // write your data here
            value: 0,
        };
    },
    methods: {
        // write your methods here
        changeValue() {
            if (this.value > 999) {
                let commas = this.value.toLocaleString("en-US");
                return commas;
            } else {
                return this.value;
            }
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
.display-container {
    background: #181f32;
    min-width: 100%;
    /* min-height: 100%; */
    height: 100%;
    max-height: 130px;
    border-radius: 10px;
    padding: 8px;
    margin: 30px auto;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    padding: 32px;
}

.display-container p {
    color: #fff;
    font-size: 60px;
    font-weight: 700;
}
</style>
