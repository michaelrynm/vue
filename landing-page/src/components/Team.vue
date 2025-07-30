<script>
import team1 from '@/assets/team1.jpg'
import team2 from '@/assets/team2.jpg'
import team3 from '@/assets/team3.jpg'
import team4 from '@/assets/team4.jpg'
import team5 from '@/assets/team5.jpg'
import team6 from '@/assets/team6.jpg'
import team7 from '@/assets/team7.jpg'
import team8 from '@/assets/team8.png'
import team9 from '@/assets/team9.jpg'
import team10 from '@/assets/team10.jpg'
import dogIcon from '@/assets/dog-logo.svg'
import catIcon from '@/assets/cat-logo.svg'

export default {
  data() {
    return {
      teamMembers: [
        {
          name: 'Darina Deriy',
          position: 'Chairman of the Board',
          image: team1,
        },
        {
          name: 'Polina Snisarenko-Kulchytska',
          position: 'Curator of the Foundation',
          image: team2,
        },
        {
          name: 'Bohdan Kulchytsky',
          position: 'Executive Manager',
          image: team3,
        },
        {
          name: 'Mykhaylo Deriy',
          position: 'Operation Manager',
          image: team4,
        },
        {
          name: 'Ksenia Nikishina',
          position: 'Office manager',
          image: team5,
        },
        {
          name: 'Anna Andriychuk',
          position: 'SMM-manager',
          image: team6,
        },
        {
          name: 'Anastasia Kovalchuk',
          position: 'Director',
          image: team7,
        },
        {
          name: 'Basil Gloo',
          position: 'Web Developer',
          image: team8,
        },
        {
          name: 'Lina Yakobchuk',
          position: 'Designer',
          image: team9,
        },
        {
          name: 'Anastasia Yevchenko',
          position: 'Translator',
          image: team10,
        },
        {
          name: 'Office Manager',
          position: 'open vacancy',
          image: dogIcon,
        },
        {
          name: 'SEO Specialist',
          position: 'open vacancy',
          image: catIcon,
        },
      ],
    }
  },
}
</script>

<template>
  <div class="team-container">
    <div>
      <p class="team-title">Our team</p>
      <p class="team-description">
        consists of completely different people who are united by a common desire - to help
      </p>
    </div>
    <div class="cards-container">
      <div class="team-cards" v-for="member in teamMembers" :key="member.name">
        <img :src="member.image" alt="Team Member" />
        <div class="team-card-content">
          <p class="team-card-name">{{ member.name }}</p>
          <p class="team-card-position">{{ member.position }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="sass">
.team-container
    padding: 10rem 12rem
    font-family: 'DM Sans', sans-serif

.team-title
    font-size: 5rem
    font-weight: 700

.team-description
    font-size: 3rem
    margin-top: 1rem
    line-height: 1.5

.cards-container
    display: grid
    grid-template-columns: repeat(4, 1fr)
    gap: 2rem 3rem
    overflow: hidden
    margin-top: 3rem

.team-cards
  position: relative
  display: flex
  flex-direction: column
  align-items: center
  justify-content: flex-start
  background-color: #fcf944
  width: 320px
  height: 500px
  padding: 2rem 2rem
  border: 0px solid black
  box-sizing: border-box
  overflow: visible

  img
    position: relative
    width: 100%
    height: 260px
    object-fit: contain
    filter: grayscale(100%)
    transition: transform 0.2s linear

  .team-card-content
    position: relative
    margin-top: 1.5rem
    width: 100%
    display: flex
    flex-direction: column
    align-items: center
    justify-content: flex-start
    transition: transform 0.2s linear

    .team-card-name
      font-size: 1.5rem
      text-align: center

    .team-card-position
      font-size: 1.5rem
      margin-top: 1rem
      text-align: center

  &::after
    content: ''
    position: absolute
    top: 0
    left: 0
    width: 100%
    height: 100%
    border: 3px solid black
    transform: translate(0, 0) scale(1)
    transition: transform 0.2s linear
    pointer-events: none
    z-index: 0
    box-sizing: border-box

  &:hover
    &::after
      transform: scale(0.85)

    .team-card-content
      transform: scale(0.95)

    img
      transform: scale(0.85)


// Desktop besar (1201px - 1600px)
@media (min-width: 1201px) and (max-width: 1600px)
  .team-container
    padding: 6rem 8rem
    max-width: 1400px
    margin: 0 auto

  .cards-container
    grid-template-columns: repeat(4, 1fr)
    gap: 2rem

  .team-cards
    width: 100%
    max-width: 260px


// Tablet besar - 3 kolom
@media (max-width: 1200px)
  .team-container
    padding: 8rem 8rem

  .cards-container
    grid-template-columns: repeat(3, 1fr)
    gap: 2rem

  .team-cards
    width: 280px
    height: 450px

  .team-title
    font-size: 4.5rem

  .team-description
    font-size: 2.5rem

// Tablet - 3 kolom
@media (max-width: 992px)

  .team-container
    padding: 6rem 4rem

  .cards-container
    grid-template-columns: repeat(3, 1fr)
    gap: 1rem



  .team-cards
    width: 200px
    height: 320px
    padding: 1rem

    .team-card-content
      .team-card-name
        font-size: 1.2rem

      .team-card-position
        font-size: 1rem

    img
      height: 220px

  .team-title
    font-size: 4rem

  .team-description
    font-size: 2.2rem

// Mobile besar - 2 kolom
@media (max-width: 768px)
  .team-container
    padding: 4rem 2rem

  .cards-container
    grid-template-columns: repeat(2, 1fr)
    gap: 1.5rem 1rem

  .team-cards
    width: 100%
    max-width: 240px
    height: 400px
    justify-self: center

    img
      height: 200px

    .team-card-content
      .team-card-name
        font-size: 1.3rem

      .team-card-position
        font-size: 1.3rem

  .team-title
    font-size: 3.5rem

  .team-description
    font-size: 2rem

// Mobile sedang - 2 kolom
@media (max-width: 576px)
  .team-container
    padding: 3rem 1.5rem

  .cards-container
    grid-template-columns: repeat(2, 1fr)
    gap: 1rem

  .team-cards
    width: 100%
    max-width: 200px
    height: 350px
    padding: 1rem

    img
      height: 180px

    .team-card-content
      margin-top: 1rem

      .team-card-name
        font-size: 1.2rem

      .team-card-position
        font-size: 1.2rem
        margin-top: 0.5rem

  .team-title
    font-size: 3rem

  .team-description
    font-size: 1.8rem

// Mobile kecil - 2 kolom (minimum)
@media (max-width: 400px)
  .team-container
    padding: 2rem 1rem

  .cards-container
    grid-template-columns: repeat(2, 1fr)
    gap: 0.8rem

  .team-cards
    width: 100%
    max-width: 160px
    height: 300px
    padding: 0.8rem

    img
      height: 150px

    .team-card-content
      .team-card-name
        font-size: 1rem

      .team-card-position
        font-size: 1rem

  .team-title
    font-size: 2.5rem

  .team-description
    font-size: 1.5rem
</style>
