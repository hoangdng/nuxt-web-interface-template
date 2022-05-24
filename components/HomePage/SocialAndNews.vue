<template>
  <div class="columns mt-4">
    <div class="column">
      <h1
        class="
          is-uppercase
          is-size-4
          has-text-black
          has-text-weight-bold
          has-text-centered
          mb-5
      ">
        Instagram
      </h1>
    </div>
    <div class="column">
      <h1
        class="
          is-uppercase
          is-size-4
          has-text-black
          has-text-weight-bold
          has-text-centered
          mb-5
      ">
        Tin tức & bài viết
      </h1>
      <div class="columns is-multiline is-mobile">
        <SocialAndNewsArticle
          v-for="(article, index) in articles.slice(0, 4)"
          :key="index"
          :thumbnail-url="article.thumbnailUrl"
          :title="article.title"
          :content="article.content"
        />
      </div>
    </div>
  </div>
</template>

<script>
import SocialAndNewsArticle from "~/components/HomePage/SocialAndNewsArticle";

export default {
  name: "SocialAndNews",
  components: {SocialAndNewsArticle},
  data() {
    return {
      articles: [
        {
          thumbnailUrl: "https://ananas.vn/wp-content/uploads/kvngang_mobile_web-300x160.jpg",
          title: "Urbas corluray pack",
          content: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci aliquid aut blanditiis consequatur,culpa ea ipsam, itaque laudantium minus sit suscipit vero. Aliquid commodi debitis deserunt distinctio error quaerat quasi!Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci aliquid aut blanditiis consequatur,culpa ea ipsam, itaque laudantium minus sit suscipit vero. Aliquid commodi debitis deserunt distinctio error quaerat quasi!"
        },
        {
          thumbnailUrl: "https://ananas.vn/wp-content/uploads/Mobile_Blog-1980s_0-300x160.jpg",
          title: "Vintas saigon 1980s",
          content: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci aliquid aut blanditiis consequatur,culpa ea ipsam, itaque laudantium minus sit suscipit vero. Aliquid commodi debitis deserunt distinctio error quaerat quasi!Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci aliquid aut blanditiis consequatur,culpa ea ipsam, itaque laudantium minus sit suscipit vero. Aliquid commodi debitis deserunt distinctio error quaerat quasi!"
        },
        {
          thumbnailUrl: "https://ananas.vn/wp-content/uploads/peeping_pattas01-300x160.jpg",
          title: "Sneaker fest vietnam và sự kết hợp",
          content: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci aliquid aut blanditiis consequatur,culpa ea ipsam, itaque laudantium minus sit suscipit vero. Aliquid commodi debitis deserunt distinctio error quaerat quasi!Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci aliquid aut blanditiis consequatur,culpa ea ipsam, itaque laudantium minus sit suscipit vero. Aliquid commodi debitis deserunt distinctio error quaerat quasi!"
        },
        {
          thumbnailUrl: "https://ananas.vn/wp-content/uploads/shoes-anatomy-thumbnail-300x160.jpg",
          title: "\"Giải phẫu\" giày Vulcanized",
          content: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci aliquid aut blanditiis consequatur,culpa ea ipsam, itaque laudantium minus sit suscipit vero. Aliquid commodi debitis deserunt distinctio error quaerat quasi!Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci aliquid aut blanditiis consequatur,culpa ea ipsam, itaque laudantium minus sit suscipit vero. Aliquid commodi debitis deserunt distinctio error quaerat quasi!"
        },
        {
          thumbnailUrl: "https://ananas.vn/wp-content/uploads/kvngang_mobile_web-300x160.jpg",
          title: "Urbas corluray pack",
          content: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci aliquid aut blanditiis consequatur,culpa ea ipsam, itaque laudantium minus sit suscipit vero. Aliquid commodi debitis deserunt distinctio error quaerat quasi!Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci aliquid aut blanditiis consequatur,culpa ea ipsam, itaque laudantium minus sit suscipit vero. Aliquid commodi debitis deserunt distinctio error quaerat quasi!"
        }
      ]
    }
  }
}
</script>
