<template>
    <div class="theme-toggle-container">
        <p>Theme</p>
        <div class="theme-toggle">
            <Theme :start="true" @click="changePosition(0)" :index="1" />
            <Theme @click="changePosition(1)" :index="2" />
            <Theme @click="changePosition(2)" :index="3" />
            <Theme @click="changePosition(3)" :index="4" />
            <Theme :end="true" @click="changePosition(4)" :index="5" />
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
            leftPos: 4,
            currentTheme: 0,
            themes: [
                {
                    backgroundColor: "#3b4664",
                    displayBackground: "#181f32",
                    displayTextColor: "#fefffd",
                    textColor: "#414755",
                    resetBtnTextColor: "#feffff",
                    btnContainerBackground: "#252d44",
                    normalBtnColor: "#eae3db",
                    normalBtnShadow: "#b5a49a",
                    normalBtnHover: "#ffffff",
                    resetBtnColor: "#647299",
                    resetBtnShadow: "#424e74",
                    resetBtnHover: "#a2b3e1",
                    equalBtnColor: "#d13f30",
                    equalBtnShadow: "#96271c",
                    equalBtnHover: "#f96c5b",
                },
                {
                    backgroundColor: "#E6E6E6",
                    displayBackground: "#EEEEEE",
                    displayTextColor: "#33332B",
                    textColor: "#393931",
                    resetBtnTextColor: "#F9FFFF",
                    btnContainerBackground: "#D3CDCD",
                    normalBtnColor: "#E5E4E0",
                    normalBtnShadow: "#A79D91",
                    normalBtnHover: "#FFFFFF",
                    resetBtnColor: "#388187",
                    resetBtnShadow: "#1C6168",
                    resetBtnHover: "#62B5BD",
                    equalBtnColor: "#C85401",
                    equalBtnShadow: "#8D3800",
                    equalBtnHover: "#FF8B38",
                },
                {
                    backgroundColor: "#0D1321",
                    displayBackground: "#1A2133",
                    displayTextColor: "#F3F3F3",
                    textColor: "#A8B3C8",
                    resetBtnTextColor: "#FFFFFF",
                    btnContainerBackground: "#2B364E",
                    normalBtnColor: "#4C5C7B",
                    normalBtnShadow: "#38425F",
                    normalBtnHover: "#5F7096",
                    resetBtnColor: "#E84855",
                    resetBtnShadow: "#B53E4B",
                    resetBtnHover: "#F06D7E",
                    equalBtnColor: "#00B4D8",
                    equalBtnShadow: "#008DA6",
                    equalBtnHover: "#33CCFF",
                },
                {
                    backgroundColor: "#17062A",
                    displayBackground: "#1E0836",
                    displayTextColor: "#FADF46",
                    textColor: "#FFE43F",
                    resetBtnTextColor: "#fffeff",
                    btnContainerBackground: "#1E0836",
                    normalBtnColor: "#331B4D",
                    normalBtnShadow: "#851C9D",
                    normalBtnHover: "#6B34AC",
                    resetBtnColor: "#56077C",
                    resetBtnShadow: "#BF15F4",
                    resetBtnHover: "#8631B0",
                    equalBtnColor: "#00DECF",
                    equalBtnShadow: "#6EF7EF",
                    equalBtnHover: "#94FFF9",
                },
                {
                    backgroundColor: "#2E2E2E",
                    displayBackground: "#1A1A1A",
                    displayTextColor: "#D4D4D4",
                    textColor: "#D4D4D4",
                    resetBtnTextColor: "#FFFFFF",
                    btnContainerBackground: "#474747",
                    normalBtnColor: "#666666",
                    normalBtnShadow: "#444444",
                    normalBtnHover: "#999999",
                    resetBtnColor: "#FF6347",
                    resetBtnShadow: "#CC4731",
                    resetBtnHover: "#FF7F66",
                    equalBtnColor: "#4CAF50",
                    equalBtnShadow: "#388E3C",
                    equalBtnHover: "#81C784",
                },
            ],
        };
    },
    components: {
        Theme,
    },
    methods: {
        // write your methods here
        changePosition(index) {
            this.leftPos = 20 * index + 4 + index + "px";
            this.currentTheme = index;
            this.changeTheme(index);
        },

        changeTheme(index) {
            document.documentElement.style.setProperty(
                "--bg-color",
                this.themes[index].backgroundColor
            );
            document.documentElement.style.setProperty(
                "--display-bg",
                this.themes[index].displayBackground
            );
            document.documentElement.style.setProperty(
                "--display-text-color",
                this.themes[index].displayTextColor
            );
            document.documentElement.style.setProperty(
                "--text-color",
                this.themes[index].textColor
            );
            document.documentElement.style.setProperty(
                "--reset-btn-text-color",
                this.themes[index].resetBtnTextColor
            );
            document.documentElement.style.setProperty(
                "--btn-container-bg",
                this.themes[index].btnContainerBackground
            );
            document.documentElement.style.setProperty(
                "--normal-btn-color",
                this.themes[index].normalBtnColor
            );
            document.documentElement.style.setProperty(
                "--normal-btn-shadow",
                this.themes[index].normalBtnShadow
            );
            document.documentElement.style.setProperty(
                "--normal-btn-hover",
                this.themes[index].normalBtnHover
            );
            document.documentElement.style.setProperty(
                "--reset-btn-color",
                this.themes[index].resetBtnColor
            );
            document.documentElement.style.setProperty(
                "--reset-btn-shadow",
                this.themes[index].resetBtnShadow
            );
            document.documentElement.style.setProperty(
                "--reset-btn-hover",
                this.themes[index].resetBtnHover
            );
            document.documentElement.style.setProperty(
                "--equal-btn-color",
                this.themes[index].equalBtnColor
            );
            document.documentElement.style.setProperty(
                "--equal-btn-shadow",
                this.themes[index].equalBtnShadow
            );
            document.documentElement.style.setProperty(
                "--equal-btn-hover",
                this.themes[index].equalBtnHover
            );
        },
    },
    mounted() {
        this.changePosition(this.currentTheme);
        this.changeTheme(this.currentTheme);
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
    color: var(--display-text-color);
    font-size: 12px;
    font-weight: 700;
    margin-top: auto;
    margin-bottom: auto;
    margin-right: 22px;
    transition: 0.7s;
    letter-spacing: 0.6px;
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
    background-color: var(--equal-btn-color);
    position: absolute;
    cursor: pointer;
    transition: 0.2s;
    left: 4px;
}

.theme-toggle-ball:hover {
    background-color: var(--equal-btn-hover);
}
</style>
