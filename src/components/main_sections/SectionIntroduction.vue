<script>
import SectionTitle from "../partials/SectionTitle.vue"
import ServiceCard from "../partials/ServiceCard.vue"
import { serviceCards } from "../../data/cardsdb"

export default {
  name: "SectionIntroduction",

  components: {
    SectionTitle,
    ServiceCard
  },

  data() {
    return {
      stats: [
        {
          num: "1.926",
          text: "finished session"
        },
        {
          num: "3.092+",
          text: "enrolled leaners"
        },
        {
          num: "200",
          text: "online instructors"
        },
        {
          num: "100%",
          text: "satisfaction rate"
        },
      ],

      serviceCards,
      
      services: [
        "Select & customize courses to your preferences",
        "Change the tutor and make arrangements",
        "Participate in events to join others",
        "Get the desired certificate delivered at house"
      ]
    }
  }
}
</script>

<template>
  <section>
    <div class="gp-container">

      <div class="row slogan justify-content-center">
        <div class="col text-center">
          <h2 class="fw-semibold">Let passion and determination be the guide along the way and develop at your own pace that's comfortable.</h2>
          <span class="fw-bold">FANNIE MORENO</span>
          <p>/Founder & CEO</p>
        </div>
      </div>
  
      <div class="row stats">
        <div v-for="(stat, index) in stats" :key="index" class="col text-center">
          <span class="fw-bold">{{ stat.num }}</span>
          <p class="fw-bold">{{ stat.text }}</p>
        </div>
      </div>
  
      <div class="row services">
  
        <div class="col">
          <div class="row row-cols-2">
  
            <div class="col col-left">
              <div class="row row-cols-1">
                <ServiceCard
                  v-for="(serviceCard, index) in serviceCards"
                  v-show="!(index % 2)"
                  :key="index"
                  :serviceCard="serviceCard"/>
              </div>
            </div>
  
            <div class="col col-right">
              <div class="row row-cols-1">
                <ServiceCard
                  v-for="(serviceCard, index) in serviceCards"
                  v-show="index % 2"
                  :key="index"
                  :serviceCard="serviceCard"/>
              </div>
            </div>
  
          </div>
        </div>
  
        <div class="col">
          <div class="main-col-right">
            <SectionTitle
              smallHeader="Together we can create"
              titleBefore="Services we"
              titleHighlighted="can provide"
              titleAfter="for my clients." />

            <ul class="list-unstyled">
              <li v-for="(service, index) in services" :key="index" class="d-flex align-items-center">
                <i class="check fa-solid fa-check"></i>
                <p class="service-txt">{{ service }}</p>
              </li>
            </ul>
            <button class="gp-btn rounded fw-bold">Get started for free</button>
          </div>
        </div>
  
      </div>

    </div>
  </section>
</template>

<style lang="scss" scoped>
@use "../../scss/partials/variables" as *; 

  section {
    background-image: url('../../assets/img/background-pattern-grid-line.png');
    padding: 315px 0 70px 0;

    .slogan {
      margin-bottom: 126px;
  
      .col {
        max-width: 750px;
    
        h2 {
          color: $my-dark-gray;
          line-height: 50px;
          margin-bottom: 38px;
        }
    
        span {
          display: block;
          font-size: 0.95rem;
          color: $my-dark-gray;
          letter-spacing: 0.15px;
          margin-bottom: 12px;
          text-transform: uppercase;
        }
    
        p {
          font-size: 0.9rem;
          color: $my-gray;
        }
      }
    }
  
    .stats {
      margin-bottom: 132px;
  
      .col {
        
        span {
          font-size: 3rem;
          color: $my-aqua;
        }
  
        p {
          color: $my-gray;
          letter-spacing: 1.2px;
          text-transform: uppercase;
        }
      }
    }
    
    .col-right {
      margin-top: 90px;
    }
    
    .main-col-right {
      padding: 226px 0 0 74px;

      ul {
        margin-bottom: 26px;

        li {
          margin-bottom: 13px;

          .check {
            color: $my-aqua;
            margin-right: 18px;
          }

          p {
            color: $my-gray;
            margin-bottom: 0;
          }
        }
      }
    }
  }


</style>