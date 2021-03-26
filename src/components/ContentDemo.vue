<template>
    <div class="card-link">
        <article class="blog-card">
            <div class="article-details">
                <h4 class="post-category">{{ category }}</h4>
                <h3 class="post-title" @click="emitFlip">{{ name }}</h3>
                <p class="post-description">{{ desc }}</p>
                <p class="post-author">{{ text }}</p>
            </div>
        </article>
    </div>
</template>

<script>
export default {
    name: "ContentDemo",
    props: {
        text: String,
    },
    data() {
        return {
            name: "What is Lorem Ipsum?",
            category: "Lorem",
            desc:
                "Lorem Ipsum is simply dummy text of the printing and typesetting industry.",
        };
    },
    methods: {
        emitFlip() {
            this.$emit("flip");
        },
    },
};
</script>

<style lang="css">
.blog-card {
    display: block;
    background: #fff;
    box-shadow: 0 0.1875rem 1.5rem rgba(0, 0, 0, 0.2);
    border-radius: 0.375rem;
    overflow: hidden;
    margin: 1rem;
}
.card-link {
    width: 30rem;
    height: 13.625rem;
    position: relative;
    display: block;
    color: inherit;
    text-decoration: none;
}
.card-link:hover .post-title {
    transition: color 0.3s ease;
    color: #e04f62;
}
.article-details {
    padding: 1.5rem;
}
.post-category {
    display: inline-block;
    text-transform: uppercase;
    font-size: 0.75rem;
    font-weight: 700;
    line-height: 1;
    letter-spacing: 0.0625rem;
    margin: 0 0 0.75rem 0;
    padding: 0 0 0.25rem 0;
    border-bottom: 0.125rem solid #ebebeb;
}
.post-title {
    transition: color 0.3s ease;
    font-size: 1.125rem;
    line-height: 1.4;
    color: #121212;
    font-weight: 700;
    margin: 0 0 0.5rem 0;
}
.post-author {
    font-size: 0.875rem;
    line-height: 1;
    margin: 1.125rem 0 0 0;
    padding: 1.125rem 0 0 0;
    border-top: 0.0625rem solid #ebebeb;
}
</style>