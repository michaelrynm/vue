<script>
import gsap from 'gsap'
import ScrollTrigger from 'gsap/ScrollTrigger'
import arrowIcon from '@/assets/arrow.png'

gsap.registerPlugin(ScrollTrigger)

export default {
  name: 'HelpSection',

  data() {
    return {
      arrowIcon,
      cardData: [
        'Shelter of Victoria Bulbyna',
        'City of faithful hearts',
        'Shelter of Natalia Tymoshenko',
        'Shelter of Jeanne Sass',
        'Shelter of Victoria Bondarenko',
        'Sterilization center',
        'Zoo chance',
        'Save lives',
        'City Center for the Treatment of Animals',
        'Society for the Protection of Animals in Summy',
        'The right to life',
        '4 paws',
        'The kingdom of cars',
        'Zvir',
        'Mercy',
        'Happy dog',
        'Give me a paw, friend',
        'Friend',
        'Hope',
        'We are for the right to life',
        'Planeta',
        'Second Life',
        'Happy shore',
        'Retrieverteam',
        'Shelter of Irina Dobrolyubova',
        'Matilda',
        'Life',
        'Second chance',
        'SOS',
        'Best friends',
      ],
    }
  },

  mounted() {
    gsap.utils.toArray('.help-cards').forEach((card) => {
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

    gsap.from('.help-button-container', {
      scrollTrigger: {
        trigger: '.help-button-container',
        start: 'top 95%',
        toggleActions: 'restart none none none',
      },
      duration: 1.2,
      x: -100,
      opacity: 0,
      ease: 'power3.out',
    })
  },
}
</script>

<template>
  <div class="help-container">
    <div class="help-content">
      <p class="help-title">We want to help</p>
      <p class="help-description">
        homeless packs, volunteers, guardians, overstayers, shelters and other organisations
      </p>
    </div>
    <div class="help-cards-container">
      <div v-for="card in cardData" class="help-cards">
        <div class="help-card-content">
          <p>{{ card }}</p>
        </div>
      </div>
    </div>
    <div class="help-button-container">
      <p class="help-button-text">apply for help</p>
      <img class="button-image" :src="arrowIcon" alt="icon" />
    </div>
  </div>
</template>

<style lang="sass" scoped>
.help-container
  background-color: rgb(252, 249, 68)
  padding: 10rem 12rem
  font-family: 'DM Sans', sans-serif

.help-title
  font-size: 5rem
  font-weight: 700

.help-description
  font-size: 3rem
  margin-top: 1rem
  line-height: 1.5

.help-cards-container
  margin-top: 4rem
  display: grid
  grid-template-columns: repeat(3, 1fr)
  gap: 4rem 2rem

.help-cards
  position: relative
  display: flex
  justify-content: center
  align-items: center
  padding: 2rem 3rem
  background-color: white
  font-size: 1.7rem
  text-align: center
  border: 0px solid black
  cursor: pointer

  .help-card-content
    transition: transform 0.3s ease
    position: relative
    z-index: 1

  &::after
    content: ''
    position: absolute
    top: 0
    left: 0
    width: 100%
    height: 100%
    border: 3px solid black
    background-color: white
    transform: translate(0, 0)
    transition: transform 0.3s ease
    pointer-events: none
    z-index: 0
    box-sizing: border-box

  &:hover
    &::after
      transform: translate(10px, -20px)

    .help-card-content
      transform: translate(10px, -20px)

.help-button-container
  margin-top: 5rem
  background-color: rgb(255, 151, 208)
  border: 3px solid black
  width: fit-content
  padding: 1rem 2rem
  display: flex
  align-items: center
  justify-content: center
  cursor: pointer

  .help-button-text
    font-size: 2rem
    font-weight: 700
    color: black
    text-align: center

  .button-image
    width: 4rem
    margin-left: 1rem
    transform: rotate(180deg)
    transition: transform 0.3s ease

  &:hover
    .button-image
      transform: rotate(180deg) translateX(-10px)

// Media Queries untuk Responsive Design

// Large Desktop (1200px ke atas)
@media (min-width: 1200px)
  .help-container
    padding: 12rem 15rem

// Medium Desktop (992px - 1199px)
@media (max-width: 1199px) and (min-width: 992px)
  .help-container
    padding: 8rem 10rem
  
  .help-title
    font-size: 4.5rem
  
  .help-description
    font-size: 2.8rem

// Tablet Landscape (768px - 991px)
@media (max-width: 991px) and (min-width: 768px)
  .help-container
    padding: 6rem 8rem
  
  .help-title
    font-size: 4rem
  
  .help-description
    font-size: 2.5rem
  
  .help-cards-container
    grid-template-columns: repeat(2, 1fr)
    gap: 3rem 1.5rem
  
  .help-cards
    padding: 1.8rem 2.5rem
    font-size: 1.5rem

// Tablet Portrait (576px - 767px)
@media (max-width: 767px) and (min-width: 576px)
  .help-container
    padding: 5rem 6rem
  
  .help-title
    font-size: 3.5rem
  
  .help-description
    font-size: 2.2rem
  
  .help-cards-container
    grid-template-columns: repeat(2, 1fr)
    gap: 2.5rem 1rem
  
  .help-cards
    padding: 1.5rem 2rem
    font-size: 1.4rem
  
  .help-button-container
    margin-top: 4rem
    padding: 0.8rem 1.5rem
    
    .help-button-text
      font-size: 1.8rem
    
    .button-image
      width: 3.5rem

// Mobile Large (480px - 575px)
@media (max-width: 575px) and (min-width: 480px)
  .help-container
    padding: 4rem 4rem
  
  .help-title
    font-size: 3rem
  
  .help-description
    font-size: 2rem
  
  .help-cards-container
    grid-template-columns: repeat(2, 1fr)
    gap: 2rem
  
  .help-cards
    padding: 1rem 2rem
    font-size: 1rem
  
  .help-button-container
    margin-top: 3.5rem
    padding: 0.8rem 1.5rem
    
    .help-button-text
      font-size: 1.6rem
    
    .button-image
      width: 3rem

// Mobile Medium (400px - 479px)
@media (max-width: 479px) and (min-width: 400px)
  .help-container
    padding: 3rem 3rem
  
  .help-title
    font-size: 2.5rem
  
  .help-description
    font-size: 1.8rem
  
  .help-cards-container
    grid-template-columns: repeat(2, 1fr)
    gap: 1.5rem
  
  .help-cards
    padding: 1.2rem 1.5rem
    font-size: 0.8rem
  
  .help-button-container
    margin-top: 3rem
    padding: 0.7rem 1.2rem
    
    .help-button-text
      font-size: 1.4rem
    
    .button-image
      width: 2.5rem

// Mobile Small (399px ke bawah)
@media (max-width: 399px)
  .help-container
    padding: 2rem 2rem
  
  .help-title
    font-size: 2rem
  
  .help-description
    font-size: 1.5rem
  
  .help-cards-container
    margin-top: 3rem
    grid-template-columns: 1fr
    gap: 1rem
  
  .help-cards
    padding: 1rem 1.2rem
    font-size: 1rem
    
    &:hover
      &::after
        transform: translate(5px, -10px)
      
      .help-card-content
        transform: translate(5px, -10px)
  
  .help-button-container
    margin-top: 2.5rem
    padding: 0.6rem 1rem
    
    .help-button-text
      font-size: 1.2rem
    
    .button-image
      width: 2rem
      margin-left: 0.5rem
    
    &:hover
      .button-image
        transform: rotate(180deg) translateX(-5px)
</style>
