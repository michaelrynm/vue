<script>
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'

gsap.registerPlugin(ScrollTrigger)

import citizen1 from '@/assets/citizen1.jpg'
import citizen2 from '@/assets/citizen2.jpg'
import citizen3 from '@/assets/citizen3.jpg'
import citizen4 from '@/assets/citizen4.jpg'
import citizen5 from '@/assets/citizen5.jpg'
import citizen6 from '@/assets/citizen6.jpg'
import citizen7 from '@/assets/citizen7.jpg'
import citizen8 from '@/assets/citizen8.jpg'
import citizen9 from '@/assets/citizen9.jpg'
import citizen10 from '@/assets/citizen10.jpg'
import citizen11 from '@/assets/citizen11.jpg'
import citizen12 from '@/assets/citizen12.jpg'
import citizen13 from '@/assets/citizen13.jpg'
import citizen14 from '@/assets/citizen14.jpg'

export default {
  data() {
    return {
      citizens: [
        {
          name: 'Oleksiy Tritenko',
          description: 'theater and film actor',
          image: citizen1,
        },
        {
          name: 'Stanislav Boklan',
          description: "People's Artist of Ukraine",
          image: citizen2,
        },
        {
          name: 'Alexander Rudinsky',
          description: 'theater and film actor',
          image: citizen3,
        },
        {
          name: 'Oksana Zhdanova',
          description: 'theater and film actress',
          image: citizen4,
        },
        {
          name: 'Natalka Denisenko',
          description: 'theater and film actress',
          image: citizen5,
        },
        {
          name: 'Maksym Samchyk',
          description: 'theater and film actor',
          image: citizen6,
        },
        {
          name: 'Kateryna Vyshneva',
          description: 'theater and film actress',
          image: citizen7,
        },
        {
          name: 'Irma Vitovska',
          description: 'Honored Actress of Ukraine',
          image: citizen8,
        },
        {
          name: 'Igor Portyanko',
          description: 'actor of theater and cinema',
          image: citizen9,
        },
        {
          name: 'Dmytro Surzhikov',
          description: 'Honored Artist of Ukraine',
          image: citizen10,
        },
        {
          name: 'Daria Barihashvili',
          description: 'theater and film actress',
          image: citizen11,
        },
        {
          name: 'Vera Kobzar',
          description: 'theater and film actress',
          image: citizen12,
        },
        {
          name: 'Andriy Fedynchyk',
          description: 'theater and film actor',
          image: citizen13,
        },
        {
          name: 'Anastasia Nesterenko',
          description: 'theater and film actress',
          image: citizen14,
        },
      ],
    }
  },

  mounted() {
    gsap.utils.toArray('.citizen-card').forEach((card) => {
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
        duration: 1,
        y: 0,
        opacity: 1,
        ease: 'power3.out',
      })
    })
  },
}
</script>

<template>
  <div class="citizen-container">
    <div>
      <p class="citizen-title">Socially active citizens</p>
      <p class="citizen-description">support us</p>
    </div>
    <div class="citizen-card-conatiner">
      <div class="citizen-card" v-for="citizen in citizens" :key="citizen.name">
        <img :src="citizen.image" alt="Citizen Image" />
        <p class="citizen-card-name">{{ citizen.name }}</p>
        <p class="citizen-card-description">{{ citizen.description }}</p>
      </div>
    </div>
  </div>
</template>

<style lang="sass">
.citizen-container
    padding: 10rem 12rem
    font-family: 'DM Sans', sans-serif
    background-color: rgb(255, 151, 208)

.citizen-title
    font-size: 5rem
    font-weight: 700

.citizen-description
    font-size: 3rem
    margin-top: 1rem
    line-height: 1.5

.citizen-card-conatiner
    margin-top: 4rem
    display: grid
    grid-template-columns: repeat(4, 1fr)
    gap: 3rem

.citizen-card
    display: flex
    flex-direction: column
    align-items: center
    justify-content: center
    img
      filter: grayscale(100%)
      width: 100%
      height: 100%
      object-fit: cover
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1)
    .citizen-card-name
      margin-top: 1.5rem
      font-size: 2rem
      font-weight: normal
    .citizen-card-description
      font-size: 1.5rem
      margin-top: 1rem

// Large Desktop (1200px+)
@media (max-width: 1199px)
    .citizen-container
        padding: 8rem 8rem
    .citizen-card-conatiner
        grid-template-columns: repeat(3, 1fr)
        gap: 2.5rem

// Tablet (768px - 1023px)
@media (max-width: 1023px)
    .citizen-container
        padding: 6rem 4rem
    .citizen-title
        font-size: 4rem
    .citizen-description
        font-size: 2.5rem
    .citizen-card-conatiner
        grid-template-columns: repeat(3, 1fr)
        gap: 2rem

// Small Tablet (600px - 767px)
@media (max-width: 767px)
    .citizen-container
        padding: 4rem 2rem
    .citizen-title
        font-size: 3.5rem
    .citizen-description
        font-size: 2rem
    .citizen-card-conatiner
        grid-template-columns: repeat(2, 1fr)
        gap: 1.5rem
    .citizen-card
        display: flex
        flex-direction: column
        align-items: center
        justify-content: center
        .citizen-card-name
            font-size: 1.8rem
        .citizen-card-description
            font-size: 1.3rem

// Mobile (maksimal 599px)
@media (max-width: 599px)
    .citizen-container
        padding: 3rem 1.5rem
    .citizen-title
        font-size: 2.5rem
    .citizen-description
        font-size: 1.5rem
    .citizen-card-conatiner
        grid-template-columns: repeat(2, 1fr)
        gap: 1rem
    .citizen-card
        display: flex
        flex-direction: column
        align-items: center
        justify-content: center
        .citizen-card-name
            text-align: center
            font-size: 1.5rem
            margin-top: 1rem
        .citizen-card-description
            font-size: 1.2rem
            text-align: center
</style>
