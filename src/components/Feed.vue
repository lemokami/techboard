<script >
import NewsArticle from './NewsArticle.vue';
export default {
    data() {
        return {
            articles: null
        };
    },
    mounted() {
        fetch("/news.json")
        .then(res =>res.json())
        .then(data => {
            this.articles = data.articles;
        });
    },
    components: { NewsArticle }
}
</script>
<template>
  <main class="p-10 grid grid-cols-1 md:grid-cols-2 xl:grid-cols-3  gap-3">
    <a v-for="article in articles" :href="article.url" :key="article.title" class=" hover:shadow-md" >
    <NewsArticle :title="article.title" :content="article.content" :image="article.urlToImage"/>
    </a> 
 </main>
</template>