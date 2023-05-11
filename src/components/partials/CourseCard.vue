<script>
export default {
  name : "CourseCard",

  props: {
    courseCard: Object
  },

  methods: {
    getImage(img) {
      return new URL(`../../assets/img/${img}`, import.meta.url).href
    }
  }
}
</script>

<template>
  <div class="col">
    <div class="course-card d-flex align-items-center rounded">

      <div class="col-auto">
        <a href="courseCard.href" class="course-card-img d-flex align-items-center justify-content-center">
          <img :src="getImage(courseCard.img)">
        </a>
      </div>

      <div class="col">
        <div class="course-card-text">
          <span v-if="courseCard.price.toUpperCase() === 'FREE' " class="price fw-bold">{{ courseCard.price }}</span>
          <span v-else class="price fw-bold">&#36;{{ courseCard.price }}<span class="price cents">.00</span></span>
          <div class="course-name">
            <a href="courseCard.href" class="fw-semibold">{{ courseCard.name }}</a>
          </div>
          <div class="course-stats">
            <span>
              <i class="stat-icon fa-regular fa-file-lines"></i>
              <span>{{ courseCard.numLessons }} Lessons</span>
            </span>
            <span>
              <i class="stat-icon fa-regular fa-user"></i>
              <span>{{ courseCard.numStudents }} Students</span>
            </span>
          </div>
        </div>
      </div>

    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../../scss/partials/variables" as *; 

  .course-card {
    padding: 18px;
    transition: all 0.4s;
    margin: 15px 0;

    &:hover {
      background-color: white;
      box-shadow: 0 0 20px 4px rgba(0,0,0,0.06);
    }

    .course-card-img {
      height: 172px;
      width: 172px;
      border-radius: 50%;
      overflow: hidden;
      margin-right: 29px;

      img {
         height: 100%;
      }
    }

    .course-card-text {

      .price {
        display: flex;
        align-items: baseline;
        font-size: 1.45rem;
        color: $my-aqua;
        text-transform: capitalize;
        margin-bottom: 6px;

        &.cents {
          font-size: 1.14rem;
        }
      }

      .course-name {

        &:hover {
          cursor: pointer;
        }

        a {
          line-height: 2rem;
          font-size: 1.27rem;
          color: $my-blue;
          transition: all 0.2s;
        }

        &:hover a {
          color: $my-aqua;
        }
      }

      .course-stats {
        margin-top: 13px;

        .stat-icon {
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