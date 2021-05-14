<template>
    <div id="app">
        <h1>{{ postsCount }}</h1>
        <div class="post" v-for="post in allPosts" :key="post.id">
            <h2>{{ post.title }}</h2>
            <p>{{ post.body }}</p>
        </div>
    </div>
</template>

<script>
import { mapGetters, mapActions } from "vuex";
export default {
    name: "App",
    computed: mapGetters(["allPosts", "postsCount"]),
    methods: mapActions(["fetchPosts"]),

    async mounted() {
        this.fetchPosts( );
    },
    components: {},
};
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
}
.post {
    max-width: 500px;
    margin: 0 auto 20px;
    padding-bottom: 20px;
    border-top: 1px solid #ccc;
}
.post p:last-child {
    margin-bottom: 0;
}
h1 {
    text-align: center;
}
</style>
