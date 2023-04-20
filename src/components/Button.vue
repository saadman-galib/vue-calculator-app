<template>
    <div class="button">
        <p>{{ button.data }}</p>
    </div>
</template>

<script>
export default {
    name: "App",
    data() {
        return {
        };
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
.button {
    width: 110px;
    height: 70px;
    background: #3a3a3a;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 12px;
    box-shadow: 0 5px 0 0 #000000;
    margin: 8px;
    cursor: pointer;
}

.button p {
    color: #fff;
    font-size: 32px;
    font-weight: 700;
}
</style>
