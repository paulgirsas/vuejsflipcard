<template>
    <div>
        <div class="fc-container">
            <transition :name="flipped ? 'op-a-flip-transition' : 'op-a-flip-transition-reversed'" mode="out-in">
                <div v-if="!flipped" key="front">
                    <slot name="front" :flip="handleFlip" />
                </div>
                <div v-else key="back">
                    <slot name="back" :flip="handleFlip" />
                </div>
            </transition>
        </div>
    </div>
</template>

<script>
export default {
    name: "FlipCard",
    data() {
        return {
            flipped: false,
        };
    },
    methods: {
        handleFlip() {
            this.flipped = !this.flipped;
        },
    },
};
</script>

<style lang="scss">
.fc-container {
    perspective: 1000px;
    transform-style: preserve-3d;
    display: inline-block;
}

.op-a-flip-transition-enter-active,
.op-a-flip-transition-reversed-enter-active {
    transition-duration: .3s;
    transition-timing-function: ease-out;
}
.op-a-flip-transition-leave-active,
.op-a-flip-transition-reversed-leave-active {
    transition-duration: .3s;
    transition-timing-function: ease-in;
}

.op-a-flip-transition-enter,
.op-a-flip-transition-reversed-leave-to {
    transform: rotateY(-90deg);
}

.op-a-flip-transition-leave-to,
.op-a-flip-transition-reversed-enter {
    transform: rotateY(90deg);
}
</style>