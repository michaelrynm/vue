<script>
import gsap from 'gsap'
import ScrollTrigger from 'gsap/ScrollTrigger'

gsap.registerPlugin(ScrollTrigger)

export default {
  name: 'AboutSection',
  mounted() {
    gsap.from('.video-container', {
      scrollTrigger: {
        trigger: '.video-container',
        start: 'top 80%',
        toggleActions: 'restart none restart none',
      },
      duration: 1,
      y: 100,
      opacity: 0,
      ease: 'power3.out',
    })
  },
}
</script>

<template>
  <div class="about-container">
    <div class="about-intro">
      <p class="intro-title">We are</p>
      <p class="intro-description">
        team of like-minded people, socially active companies, media personalities, volunteers who
        help low-income shelters and foster carers to support homeless animals.
      </p>
    </div>
    <div class="about-goal">
      <p class="goal-title">Our primary goal</p>
      <p class="goal-description">
        is to provide animals with the most necessary things - food, medicine, and urgent needs for
        the livelihood of shelters. We believe in our power and the power of conscious citizens who
        care about the environment and their health, who understand the importance of helping each
        other, especially our little friends. Growth begins with your care for your loved ones.
        Animals are one of the closest creatures to humans who remain with us throughout our lives.
        We all know the healing power of warmth, grace, and big loving eyes.
      </p>
      <div class="goal-quote">
        <p class="quote-text">
          "Animals need to have friends. Just like humans." <br />
          - James Herriot, All Creatures Great and Small
        </p>
      </div>
      <p class="goal-call">
        Who else if not we should support our younger brothers, especially in difficult times? Let's
        be friends!
      </p>
    </div>
    <div class="video-container">
      <iframe
        width="100%"
        height="850"
        src="https://www.youtube.com/embed/5Wk1rp99B7o"
        title="YouTube video player"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
        allowfullscreen
      ></iframe>
    </div>
  </div>
</template>

<style lang="sass">
body
  font-family: 'DM Sans', sans-serif

.about-container
  padding: 10rem 12rem

  // Tablet landscape
  @media screen and (max-width: 1024px)
    padding: 8rem 6rem

  // Tablet portrait
  @media screen and (max-width: 768px)
    padding: 6rem 4rem

  // Mobile landscape
  @media screen and (max-width: 640px)
    padding: 4rem 2rem

  // Mobile portrait
  @media screen and (max-width: 480px)
    padding: 3rem 1.5rem

.about-intro
  .intro-title
    font-size: 5rem
    font-weight: 700

    // Tablet landscape
    @media screen and (max-width: 1024px)
      font-size: 4rem

    // Tablet portrait
    @media screen and (max-width: 768px)
      font-size: 3.5rem

    // Mobile landscape
    @media screen and (max-width: 640px)
      font-size: 2.8rem

    // Mobile portrait
    @media screen and (max-width: 480px)
      font-size: 2.2rem

    // Small mobile
    @media screen and (max-width: 360px)
      font-size: 1.8rem

  .intro-description
    font-size: 3rem
    margin-top: 1rem
    line-height: 1.5

    // Tablet landscape
    @media screen and (max-width: 1024px)
      font-size: 2.5rem

    // Tablet portrait
    @media screen and (max-width: 768px)
      font-size: 2rem

    // Mobile landscape
    @media screen and (max-width: 640px)
      font-size: 1.6rem

    // Mobile portrait
    @media screen and (max-width: 480px)
      font-size: 1.3rem
      line-height: 1.4

    // Small mobile
    @media screen and (max-width: 360px)
      font-size: 1.1rem

.about-goal
  .goal-title
    font-size: 5rem
    font-weight: 700
    margin-top: 4rem

    // Tablet landscape
    @media screen and (max-width: 1024px)
      font-size: 4rem
      margin-top: 3rem

    // Tablet portrait
    @media screen and (max-width: 768px)
      font-size: 3.5rem
      margin-top: 2.5rem

    // Mobile landscape
    @media screen and (max-width: 640px)
      font-size: 2.8rem
      margin-top: 2rem

    // Mobile portrait
    @media screen and (max-width: 480px)
      font-size: 2.2rem
      margin-top: 1.5rem

    // Small mobile
    @media screen and (max-width: 360px)
      font-size: 1.8rem

  .goal-description
    font-size: 3rem
    margin-top: 1rem
    line-height: 1.5

    // Tablet landscape
    @media screen and (max-width: 1024px)
      font-size: 2.5rem

    // Tablet portrait
    @media screen and (max-width: 768px)
      font-size: 2rem

    // Mobile landscape
    @media screen and (max-width: 640px)
      font-size: 1.6rem

    // Mobile portrait
    @media screen and (max-width: 480px)
      font-size: 1.3rem
      line-height: 1.4

    // Small mobile
    @media screen and (max-width: 360px)
      font-size: 1.1rem

.goal-quote
  padding: 3rem 5rem

  // Tablet landscape
  @media screen and (max-width: 1024px)
    padding: 2.5rem 4rem

  // Tablet portrait
  @media screen and (max-width: 768px)
    padding: 2rem 3rem

  // Mobile landscape
  @media screen and (max-width: 640px)
    padding: 1.5rem 2rem

  // Mobile portrait
  @media screen and (max-width: 480px)
    padding: 1rem 1.5rem

  .quote-text
    border-left: 3px solid rgb(255, 151, 208)
    padding-left: 1rem
    font-size: 3rem
    line-height: 1.5

    // Tablet landscape
    @media screen and (max-width: 1024px)
      font-size: 2.5rem

    // Tablet portrait
    @media screen and (max-width: 768px)
      font-size: 2rem

    // Mobile landscape
    @media screen and (max-width: 640px)
      font-size: 1.6rem
      padding-left: 0.8rem

    // Mobile portrait
    @media screen and (max-width: 480px)
      font-size: 1.3rem
      line-height: 1.4
      padding-left: 0.7rem

    // Small mobile
    @media screen and (max-width: 360px)
      font-size: 1.1rem
      padding-left: 0.6rem

.goal-call
  font-size: 3rem
  margin-top: 2rem
  line-height: 1.5

  // Tablet landscape
  @media screen and (max-width: 1024px)
    font-size: 2.5rem
    margin-top: 1.5rem

  // Tablet portrait
  @media screen and (max-width: 768px)
    font-size: 2rem

  // Mobile landscape
  @media screen and (max-width: 640px)
    font-size: 1.6rem
    margin-top: 1rem

  // Mobile portrait
  @media screen and (max-width: 480px)
    font-size: 1.3rem
    line-height: 1.4

  // Small mobile
  @media screen and (max-width: 360px)
    font-size: 1.1rem

.video-container
  margin-top: 3rem

  // Tablet landscape
  @media screen and (max-width: 1024px)
    margin-top: 2.5rem

  // Tablet portrait
  @media screen and (max-width: 768px)
    margin-top: 2rem

  // Mobile landscape
  @media screen and (max-width: 640px)
    margin-top: 1.5rem
    iframe
      height: 300px

  // Mobile portrait
  @media screen and (max-width: 480px)
    margin-top: 1rem
    iframe
      height: 250px
</style>
