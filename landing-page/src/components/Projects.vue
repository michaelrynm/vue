<script>
import gsap from 'gsap'
import ScrollTrigger from 'gsap/ScrollTrigger'

gsap.registerPlugin(ScrollTrigger)

export default {
  name: 'ProjectsSection',
  data() {
    return {
      projects: [
        {
          title: 'Emergency Aid. WAR 2022.',
          description:
            'providing food and medicine to the shelters and animals which lost their homes and families due to the war',
          backgroundColor: '#000000',
        },
        {
          title: 'Non-commercial feed line',
          description:
            'construction of industrial production base where food for shelters will be produced on a free basis',
          backgroundColor: '#31be32',
        },
        {
          title: 'Educational and Control',
          description:
            'lectures on communication, organisation and coordination of processes, control over the use of aid',
          backgroundColor: '#ff97d0',
        },
      ],
    }
  },
  mounted() {
    gsap.utils.toArray('.project-card').forEach((card) => {
      gsap.from(card, {
        scrollTrigger: {
          trigger: card,
          start: 'top 80%',
          toggleActions: 'restart none restart none',
        },
        duration: 1,
        x: -100,
        opacity: 0,
        ease: 'power3.out',
      })
    })
  },
}
</script>

<template>
  <div class="projects-container">
    <div>
      <p class="project-title">Our projects</p>
      <p class="project-description">
        are very different in terms of priority, scale and complexity of implementation
      </p>
    </div>
    <div
      v-for="project in projects"
      :key="project.title"
      class="project-card"
      :style="{ backgroundColor: project.backgroundColor }"
    >
      <div class="project-card-content">
        <p class="project-card-title">{{ project.title }}</p>
        <p class="project-card-description">{{ project.description }}</p>
      </div>
    </div>
  </div>
</template>

<style lang="sass">
body
  font-family: 'DM Sans', sans-serif

.projects-container
  padding: 10rem 12rem
  background-color: rgb(62, 136, 255)
  
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

.project-title
  font-size: 5rem
  font-weight: 700
  color: white
  
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

.project-description
  font-size: 3rem
  color: white
  margin-top: 2rem
  
  // Tablet landscape
  @media screen and (max-width: 1024px)
    font-size: 2.5rem
  
  // Tablet portrait
  @media screen and (max-width: 768px)
    font-size: 2rem
    margin-top: 1.5rem
  
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

.project-card
  position: relative
  padding: 3.5rem
  background: black
  margin-top: 3rem
  transition: border-color 0.3s ease
  
  // Tablet landscape
  @media screen and (max-width: 1024px)
    padding: 3rem
    margin-top: 2.5rem
  
  // Tablet portrait
  @media screen and (max-width: 768px)
    padding: 2.5rem
    margin-top: 2rem
  
  // Mobile landscape
  @media screen and (max-width: 640px)
    padding: 2rem
    margin-top: 1.5rem
  
  // Mobile portrait
  @media screen and (max-width: 480px)
    padding: 1.5rem
    margin-top: 1rem

  .project-card-content
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
    border: 3px solid #ffffff
    transform: translate(0, 0)
    transition: transform 0.3s ease
    pointer-events: none
    z-index: 0
    box-sizing: border-box
    
    // Mobile portrait - reduce border thickness
    @media screen and (max-width: 480px)
      border: 2px solid #ffffff

  &:hover
    // Disable hover effects on touch devices
    @media (hover: hover) and (pointer: fine)
      &::after
        transform: translate(10px, -20px)
        
        // Reduce transform distance on smaller screens
        @media screen and (max-width: 768px)
          transform: translate(8px, -15px)
        
        @media screen and (max-width: 480px)
          transform: translate(6px, -12px)

      .project-card-content
        transform: translate(10px, -20px)
        
        // Reduce transform distance on smaller screens
        @media screen and (max-width: 768px)
          transform: translate(8px, -15px)
        
        @media screen and (max-width: 480px)
          transform: translate(6px, -12px)

  .project-card-title
    font-size: 3.5rem
    font-weight: 700
    color: white
    
    // Tablet landscape
    @media screen and (max-width: 1024px)
      font-size: 3rem
    
    // Tablet portrait
    @media screen and (max-width: 768px)
      font-size: 2.5rem
    
    // Mobile landscape
    @media screen and (max-width: 640px)
      font-size: 2rem
    
    // Mobile portrait
    @media screen and (max-width: 480px)
      font-size: 1.6rem
    
    // Small mobile
    @media screen and (max-width: 360px)
      font-size: 1.4rem

  .project-card-description
    font-size: 2.5rem
    color: white
    margin-top: 1rem
    
    // Tablet landscape
    @media screen and (max-width: 1024px)
      font-size: 2rem
    
    // Tablet portrait
    @media screen and (max-width: 768px)
      font-size: 1.8rem
    
    // Mobile landscape
    @media screen and (max-width: 640px)
      font-size: 1.4rem
      margin-top: 0.8rem
    
    // Mobile portrait
    @media screen and (max-width: 480px)
      font-size: 1.1rem
      line-height: 1.4
      margin-top: 0.6rem
    
    // Small mobile
    @media screen and (max-width: 360px)
      font-size: 1rem
      margin-top: 0.4rem
      
</style>
