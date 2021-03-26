# VueJS FlipCard
<!-- ABOUT THE PROJECT -->
## About The Project

This project was buid to demonstrate the usage of `FlipCard.vue` component.

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

<!-- USAGE EXAMPLES -->
## Usage

To use FlipCard, provide content to `front` and `back` slots.

Content (front and back) can emmit `fc-flip` to trigger flip animation to occur.
1. Import FlipCard
   ```JS
   import FlipCard from "./components/FlipCard.vue";
   ```

2. Provide data
   ```JS
   <flip-card v-for="item in demo_items" :key="item.id">
      <template #front="{ flip }">
          <content-demo @fc-flip="flip"/>
      </template>
      <template #back="{ flip }">
          <content-demo @fc-flip="flip"/>
      </template>
   </flip-card>
   ```
  
3. Trigger flip from content
   ```JS
   this.$emit("fc-flip");
   ```
