<template>
    <div
        class="theme"
        :style="{
            borderRadius: `${isStart()} ${isEnd()} ${isEnd()} ${isStart()}`,
        }"
    >
        <div class="label">
            <p>
                {{ index }}
            </p>
        </div>
    </div>
</template>

<script>
export default {
    name: "App",
    data() {
        return {};
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
        index: {
            type: String,
            default: "1",
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
    background: var(--btn-container-bg);
    width: 22px;
    height: 22px;
    cursor: pointer;
    position: relative;
}

.theme > .label p {
    position: absolute;
    color: var(--display-text-color);
    top: calc(-50% - 4px);
    left: 40%;
    margin: 0;
    font-size: 12px;
}
</style>
