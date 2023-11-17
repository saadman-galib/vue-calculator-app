<template>
    <div class="display-container">
        <p :style="{ fontSize: textSize + 'px' }">
            {{ changeValue() }}
        </p>
    </div>
</template>

<script>
import debounce from 'lodash/debounce';


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
    computed: {},

    methods: {
        debouncedCalculateFontSize: debounce(function (singleLetterWidthPerPx, currentWidth, maxWidth) {
            if (currentWidth < maxWidth) {
                return this.isDesktop ? 62 : 42;
            }
            else{

                const newFontSize =
                    maxWidth / (singleLetterWidthPerPx * this.value.length);
                    
                return newFontSize;
            }
  }, 200),
        },
        changeValue() {
            this.value = this.display;

            const currentFontSize = this.textSize;
            const singleLetterWidthPerPx = 0.562506;

            if (this.isDesktop) {
                const currentWidth =
                    singleLetterWidthPerPx *
                    currentFontSize *
                    this.value.length;
                const maxWidth = 523.13;

                this.textSize = this.debouncedCalculateFontSize(
                    singleLetterWidthPerPx,
                    currentWidth,
                    maxWidth
                );
            } else {
                const currentWidth =
                    singleLetterWidthPerPx *
                    currentFontSize *
                    this.value.length;
                const maxWidth = 283.5;
                this.textSize = this.debouncedCalculateFontSize(
                    singleLetterWidthPerPx,
                    currentWidth,
                    maxWidth
                );
            }

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
        font-size: 40px;
    }
}
</style>
