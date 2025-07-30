<script>
import gsap from 'gsap'

// Import logo
import catLogo from '../assets/cat-logo.svg'
import dogLogo from '../assets/dog-logo.svg'
import facebookIcon from '../assets/facebook.svg'
import telegramIcon from '../assets/telegram.svg'
import youtubeIcon from '../assets/youtube.svg'
import patreonIcon from '../assets/patreon.svg'
import instagramIcon from '../assets/instagram.svg'

export default {
  name: 'HeroSection',
  data() {
    return {
      logos: [catLogo, dogLogo],
      youtubeIcon,
      instagramIcon,
      facebookIcon,
      patreonIcon,
      telegramIcon,
    }
  },
  mounted() {
    const slides = document.querySelectorAll('.logo-slide')

    slides.forEach((slide, i) => {
      gsap.set(slide, {
        opacity: i === 0 ? 1 : 0,
        y: 0,
        zIndex: i === 0 ? 2 : 1,
      })
    })

    const timeline = gsap.timeline({
      repeat: -1,
      defaults: { duration: 0.8, ease: 'power2.inOut' },
    })

    this.logos.forEach((_, i) => {
      const nextIndex = (i + 1) % this.logos.length

      timeline
        .to(
          `.logo-slide-${i}`,
          {
            y: 100,
            opacity: 0,
            zIndex: 1,
          },
          '+=2',
        )
        .set(`.logo-slide-${i}`, { y: 0 })
        .to(
          `.logo-slide-${nextIndex}`,
          {
            opacity: 1,
            zIndex: 2,
          },
          '<',
        )
    })
  },
}
</script>

<template>
  <section class="hero-section">
    <div class="hero-content">
      <!-- LOGO SLIDE -->
      <div class="hero-image-container">
        <div class="logo-wrapper">
          <div
            v-for="(logo, index) in logos"
            :key="index"
            :class="`logo-slide logo-slide-${index}`"
          >
            <img :src="logo" alt="Logo" />
          </div>
        </div>
      </div>

      <!-- TITLE -->
      <div class="hero-title">
        <p>Innovative</p>
        <p>Solutions</p>
        <p>for</p>
        <p>Animals</p>
      </div>
    </div>

    <!-- SUBTITLE & ICONS -->
    <div class="hero-subtitle">
      <p>charity organization</p>
    </div>
    <div class="hero-icons">
      <img :src="youtubeIcon" alt="youtube icon" />
      <img :src="instagramIcon" alt="instagram icon" />
      <img :src="facebookIcon" alt="facebook icon" />
      <img :src="patreonIcon" alt="patreon icon" />
      <img :src="telegramIcon" alt="telegram icon" />
    </div>
  </section>
</template>

<style scoped lang="sass">
.hero-section
  min-height: 100vh
  background-color: rgb(252, 249, 68)
  display: flex
  flex-direction: column
  align-items: center
  justify-content: center
  gap: 1.5rem
  padding: 2rem

  .hero-content
    display: flex
    align-items: center
    gap: 2rem

    .hero-image-container
      width: 250px
      height: 270px
      overflow: hidden
      position: relative

      .logo-wrapper
        position: relative
        width: 100%
        height: 100%

      .logo-slide
        position: absolute
        width: 100%
        height: 100%
        top: 0
        left: 0
        opacity: 0

        img
          width: 100%
          height: 100%
          object-fit: contain

    .hero-title
      text-align: left
      line-height: 4.5rem

      p
        font-family: 'DM Sans', sans-serif
        font-size: 5rem
        font-weight: bold
        margin: 0.2rem

  .hero-subtitle
    margin-top: 1rem
    font-size: 3rem
    font-family: 'DM Sans', sans-serif

  .hero-icons
    img
      width: 3rem
      height: 3rem
      margin: 0 0.5rem
      cursor: pointer
      transition: transform 0.3s

      &:hover
        transform: scale(0.75)

// Tablet landscape dan desktop kecil (768px - 1024px)
@media screen and (max-width: 1024px)
  .hero-section
    padding: 1.5rem
    gap: 1.2rem

    .hero-content
      gap: 1.5rem

      .hero-image-container
        width: 220px
        height: 240px

      .hero-title
        line-height: 4rem

        p
          font-size: 4.2rem

    .hero-subtitle
      font-size: 2.5rem

    .hero-icons
      img
        width: 2.5rem
        height: 2.5rem

// Tablet portrait (768px ke bawah)
@media screen and (max-width: 768px)
  .hero-section
    padding: 1rem
    gap: 1rem

    .hero-content
      flex-direction: row
      justify-content: center
      gap: 1.5rem
      text-align: center

      .hero-image-container
        width: 200px
        height: 220px

      .hero-title
        text-align: left
        line-height: 3.5rem

        p
          font-size: 3.5rem

    .hero-subtitle
      font-size: 2rem
      text-align: center

    .hero-icons
      margin-top: 0.5rem

      img
        width: 2.2rem
        height: 2.2rem
        margin: 0 0.3rem

// Mobile landscape (576px ke bawah)
@media screen and (max-width: 576px)
  .hero-section
    padding: 0.8rem
    gap: 0.8rem

    .hero-content
      .hero-image-container
        width: 150px
        height: 200px

      .hero-title
        line-height: 2rem

        p
          font-size: 2rem
          margin: 0.1rem

    .hero-subtitle
      font-size: 1.6rem
      margin-top: 0.5rem

    .hero-icons
      img
        width: 2rem
        height: 2rem
        margin: 0 0.25rem

// Mobile portrait kecil (400px ke bawah)
@media screen and (max-width: 400px)
  .hero-section
    padding: 0.5rem
    gap: 0.6rem

    .hero-content
      .hero-image-container
        width: 100px
        height: 200

      .hero-title
        line-height: 2.5rem

        p
          font-size: 2.2rem

    .hero-subtitle
      font-size: 1.3rem

    .hero-icons
      img
        width: 1.8rem
        height: 1.8rem
        margin: 0 0.2rem
</style>
