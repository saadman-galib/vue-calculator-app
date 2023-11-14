<template>
    <div class="display-container">
        <p :style="{ fontSize: textSize + 'px' }">
            {{ changeValue() }}
        </p>
    </div>
</template>

<script>
export default {
    name: "App",
    data() {
        return {
            value: this.display,
            textSize: 62,
            isDesktop: window.innerWidth > 645,
        };
    },
    props: {
        display: {
            required: true,
        },
    },
    methods: {
        calculateFontSize(
            currentFontSize,
            singleLetterWidthPerPx,
            currentWidth,
            maxWidth
        ) {
            if (currentWidth < maxWidth) {
                console.log("under 15");
                return 62;
            }

            console.log("not more");
            const newFontSize =
                maxWidth / (singleLetterWidthPerPx * this.value.length);

            return newFontSize;
        },
        changeValue() {
            this.value = this.display;
            // if (this.value.length > 8
            // // 16
            // ) {
            //     this.textSize = 40 - (this.value.length - 8) * 2.2;
            //     console.log(this.fontSize);
            // }
            // if (this.value > 999) {
            //     let commas = this.value.toLocaleString("en-US");
            //     return commas;
            // } else {
            //     return this.value;
            // }

            const currentFontSize = this.textSize;
            const singleLetterWidthPerPx = 0.562506;
            const currentWidth =
                singleLetterWidthPerPx * currentFontSize * this.value.length;
            const maxWidth = 523.13;
            const additionalLetter = 1;
            console.log(currentWidth);

            this.textSize = this.calculateFontSize(
                currentFontSize,
                singleLetterWidthPerPx,
                currentWidth,
                maxWidth
            );

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
    overflow: hidden;
}

.display-container p {
    color: var(--display-text-color);
    font-size: 60px;
    font-weight: 700;
    transition: 0.7s;
    /* height: 45px; */
}

/* @media (max-width: 645px) {
    .display-container p {
         font-size: 40px; 
        height: 30px;
    }
} */
</style>
