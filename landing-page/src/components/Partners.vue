<script>
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
gsap.registerPlugin(ScrollTrigger)

import partner1 from '@/assets/partner1.jpg'
import partner2 from '@/assets/partner2.png'
import partner3 from '@/assets/partner3.png'
import partner4 from '@/assets/partner4.png'
import partner5 from '@/assets/partner5.png'
import partner6 from '@/assets/partner6.jpeg'

export default {
  name: 'Partners',

  data() {
    return {
      partners: [
        {
          name: 'Partner One',
          image: partner1,
        },
        {
          name: 'Partner Two',
          image: partner2,
        },
        {
          name: 'Partner Three',
          image: partner3,
        },
        {
          name: 'Partner Four',
          image: partner4,
        },
        {
          name: 'Partner Five',
          image: partner5,
        },
        {
          name: 'Partner Six',
          image: partner6,
        },
      ],
    }
  },

  mounted() {
    gsap.utils.toArray('.partner-card').forEach((card) => {
      gsap.set(card, {
        y: 100,
        opacity: 0,
      })

      gsap.to(card, {
        scrollTrigger: {
          trigger: card,
          start: 'top 100%',
          end: 'bottom 0%',
          toggleActions: 'restart none restart none',
        },
        y: 0,
        opacity: 1,
        duration: 1,
        ease: 'power3.out',
      })
    })
  },
}
</script>

<template>
  <div class="partners-container">
    <div>
      <p class="partner-title">Our partners</p>
      <p class="partner-description">are take care of our fund and help us with many questions</p>
    </div>
    <div class="partners-list">
      <div v-for="partner in partners" :key="partner.name" class="partner-card">
        <img :src="partner.image" :alt="partner.name" />
      </div>
    </div>
  </div>
</template>

<style lang="sass">
.partners-container
    padding: 10rem 12rem
    font-family: 'DM Sans', sans-serif

.partner-title
    font-size: 5rem
    font-weight: 700

.partner-description
    font-size: 3rem
    margin-top: 1rem
    line-height: 1.5

.partners-list
  display: grid
  grid-template-columns: repeat(4, 1fr)
  gap: 2rem // beri jarak antar kartu
  width: 100%
  max-width: 100%
  box-sizing: border-box
  margin-top: 3rem

  .partner-card
    width: 100%
    overflow: hidden
    display: flex
    align-items: center
    justify-content: center
    padding: 1rem

    img
      width: 100%
      height: auto
      filter: grayscale(100%)
      object-fit: contain

// Media Queries for Responsive Design

// Large Desktop (1440px and up)
@media (min-width: 1440px)
  .partners-container
    padding: 12rem 15rem

  .partner-title
    font-size: 6rem

  .partner-description
    font-size: 3.5rem

  .partners-list
    gap: 3rem

// Desktop (1024px to 1439px)
@media (max-width: 1439px) and (min-width: 1024px)
  .partners-container
    padding: 8rem 10rem

  .partner-title
    font-size: 4.5rem

  .partner-description
    font-size: 2.8rem

  .partners-list
    gap: 2rem

// Tablet (768px to 1023px)
@media (max-width: 1023px) and (min-width: 768px)
  .partners-container
    padding: 6rem 4rem

  .partner-title
    font-size: 3.5rem

  .partner-description
    font-size: 2.2rem

  .partners-list
    grid-template-columns: repeat(3, 1fr)
    gap: 1.5rem
    margin-top: 2.5rem

// Small Tablet (600px to 767px)
@media (max-width: 767px) and (min-width: 600px)
  .partners-container
    padding: 4rem 3rem

  .partner-title
    font-size: 2.8rem

  .partner-description
    font-size: 1.8rem

  .partners-list
    grid-template-columns: repeat(2, 1fr)
    gap: 1.5rem
    margin-top: 2rem

    .partner-card
      padding: 0.8rem

// Mobile Large (480px to 599px)
@media (max-width: 599px) and (min-width: 480px)
  .partners-container
    padding: 3rem 2rem

  .partner-title
    font-size: 2.4rem

  .partner-description
    font-size: 1.6rem

  .partners-list
    grid-template-columns: repeat(2, 1fr)
    gap: 1rem
    margin-top: 2rem

    .partner-card
      padding: 0.6rem

// Mobile Small (320px to 479px)
@media (max-width: 479px) and (min-width: 320px)
  .partners-container
    padding: 2rem 1.5rem

  .partner-title
    font-size: 2rem

  .partner-description
    font-size: 1.4rem

  .partners-list
    grid-template-columns: 1fr
    gap: 1rem
    margin-top: 1.5rem

    .partner-card
      padding: 0.5rem

// Extra Small Mobile (below 320px)
@media (max-width: 319px)
  .partners-container
    padding: 1.5rem 1rem

  .partner-title
    font-size: 1.8rem

  .partner-description
    font-size: 1.2rem

  .partners-list
    grid-template-columns: 1fr
    gap: 0.8rem
    margin-top: 1rem

    .partner-card
      padding: 0.4rem
</style>
