<template>
    <div class="display-container">
        <p :style="{ fontSize: textSize + 'px' }">
            {{ value }}
        </p>
    </div>
</template>

<script>
export default {
    name: "App",
    data() {
        return {
            value: this.display,
            isDesktop: window.innerWidth > 645,
            textSize: this.isDesktop ? 62 : 42,
        };
    },
    props: {
        display: {
            required: true,
        },
    },
    methods: {
        calculateFontSize: async function (
            singleLetterWidthPerPx,
            currentWidth,
            maxWidth
        ) {
            if (currentWidth < maxWidth) {
                return this.isDesktop ? 62 : 42;
            }

            return new Promise((resolve) => {
                setTimeout(() => {
                    const newFontSize =
                        maxWidth / (singleLetterWidthPerPx * this.value.length);
                    resolve(newFontSize);
                }, 0);
            });
        },

        async changeValue() {
            this.value = this.display;

            const currentFontSize = this.textSize;
            const singleLetterWidthPerPx = 0.562506;

            const currentWidth =
                singleLetterWidthPerPx * currentFontSize * this.value.length;
            const maxWidth = this.isDesktop ? 523.13 : 283.5;

            try {
                this.textSize = await this.calculateFontSize(
                    singleLetterWidthPerPx,
                    currentWidth,
                    maxWidth
                );
            } catch (error) {
                console.error("Error calculating font size:", error);
            }
            
            

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
        },
    },
    mounted() {
        this.changeValue()
    },
    watch: {
        display() {
            this.changeValue();
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
    font-size: 62px;
    font-weight: 700;
    transition: 0.7s;
    /* height: 45px; */
}

@media (max-width: 645px) {
    .display-container {
        padding: 26px 20px;
        height: 110px;
    }

    .display-container p {
        font-size: 42px;
    }
}
</style>
