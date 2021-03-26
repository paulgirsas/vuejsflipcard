<template>
    <div id="app">
        <flip-card v-for="item in demo_items" :key="item.id">
            <template #front="{ flip }">
                <content-demo :text="item.front" @flip="flip"/>
            </template>

            <template #back="{ flip }">
                <content-demo :text="item.back" @flip="flip"/>
            </template>
        </flip-card>
    </div>
</template>

<script>
import ContentDemo from "./components/ContentDemo.vue";
import FlipCard from "./components/FlipCard.vue";

export default {
    name: "App",
    components: { FlipCard, ContentDemo },
    data() {
        return {
            demo_items: [
                {
                    id: 1,
                    front:
                        "Lorem ipsum dolor sit amet, consectetur adipiscing elit",
                    back:
                        "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.",
                },
                {
                    id: 2,
                    front: "same size front",
                    back: "same size back",
                },
            ],
        };
    },
};
</script>
