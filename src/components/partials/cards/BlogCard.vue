<script>
export default {
  name: "BlogCard",

  props: {
    blogCard: Object
  },

  methods: {
    getImage(img) {
      return new URL(`../../../assets/img/${img}`, import.meta.url).href
    }
  }
}
</script>

<template>
  <div class="col px-0">
    <div class="blog-card">

      <a href="#" class="blog-card-img d-flex align-items-center justify-content-center rounded">
        <img :src="getImage(blogCard.img)">
      </a>

      <div class="blog-card-text">
        <a :href="blogCard.categoryHref" class="blog-category fw-medium">{{ blogCard.category }}</a>
        <div class="blog-title">
          <a :href="blogCard.href" class="fw-semibold">{{ blogCard.title }}</a>
        </div>
        <div class="blog-stats">
          <span>
            <i class="blog-icon fa-regular fa-calendar"></i>
            <span>{{ blogCard.date }}</span>
          </span>
          <span>
            <i class="blog-icon fa-regular fa-eye"></i>
            <span>{{ blogCard.views }} views</span>
          </span>
        </div>
      </div>

    </div>
  </div>
</template>

<style lang="scss" scoped>
  @use "../../../scss/partials/variables" as *; 

  .blog-card {
    padding-left: 12px;
    transition: all 0.3s;

    .blog-card-img {
      height: 251px;
      width: 370px;
      overflow: hidden;
      margin-bottom: 24px;

      img {
        height: 100%;
        transition: all 1s;
      }

      &:hover img {
        transform: scale(1.1)
      }
    }

    .blog-card-text {

      .blog-category {
        text-transform: uppercase;
        color: $my-gray;
        letter-spacing: 1.2px;
        transition: all 0.3s;

        &:hover {
          color: $my-aqua;
        }
      }

      .blog-title {
        margin: 6px 0 20px 0;
        padding-right: 25px;

        &:hover {
          cursor: pointer;
        }

        a {
          line-height: 2.3rem;
          font-size: 1.5rem;
          color: $my-dark-gray;
          transition: all 0.3s;
        }

        &:hover a {
          color: $my-aqua;
        }
      }

      .blog-stats {
        margin-top: 13px;

        .blog-icon {
          margin-right: 6px;
        }

        span {
          font-size: 0.9rem;
          margin-right: 20px;
          color: $my-light-gray;
        }
      }
      
    }
  }
</style>