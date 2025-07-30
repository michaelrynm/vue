<script>
import facebookIcon from '../assets/facebook.svg'
import telegramIcon from '../assets/telegram.svg'
import youtubeIcon from '../assets/youtube.svg'
import patreonIcon from '../assets/patreon.svg'
import instagramIcon from '../assets/instagram.svg'
import footerIcon from '../assets/footerIcon.svg'

export default {
  name: 'FooterSection',
  data() {
    return {
      footerIcon,
      icons: [youtubeIcon, instagramIcon, facebookIcon, patreonIcon, telegramIcon],
    }
  },
}
</script>

<template>
  <div class="footer-container">
    <div class="footer-left">
      <p class="contact-title">Contact us</p>
      <p class="contact-description">Kyiv, Ukraine</p>
      <p class="contact-email">mail@isa.co.ua</p>

      <div class="social-icons">
        <img
          v-for="icon in icons"
          :key="icon"
          :src="icon"
          :alt="`Icon ${icon}`"
          class="social-icon"
        />
      </div>
    </div>

    <div class="footer-right">
      <img :src="footerIcon" alt="footer illustration" class="footer-icon" />
    </div>
  </div>
</template>

<style lang="sass">
.footer-container
  display: flex
  justify-content: space-between
  align-items: center
  padding: 10rem 12rem
  background-color: rgb(49, 190, 50)
  font-family: 'DM Sans', sans-serif

.footer-left
  display: flex
  flex-direction: column
  color: black

.contact-title
  font-size: 5rem
  font-weight: 700

.contact-description,
.contact-email
  font-size: 3rem

.social-icons
  display: flex
  gap: 1.5rem
  margin-top: 1rem

.social-icon
  margin-top: 1rem
  width: 3rem
  height: 3rem
  cursor: pointer
  transition: transform 0.3s ease

  &:hover
    transform: scale(0.85)

.footer-right
  display: flex
  justify-content: flex-end
  align-items: center
  flex-shrink: 0
  width: 50%

.footer-icon
  width: 100%
  height: auto
  display: block

// Media Queries untuk Responsive Design

// Desktop Large (1200px ke atas)
@media (min-width: 1200px)
  .footer-container
    padding: 10rem 12rem

// Desktop Medium (992px - 1199px)
@media (max-width: 1199px)
  .footer-container
    padding: 8rem 8rem
  
  .contact-title
    font-size: 4.5rem
  
  .contact-description,
  .contact-email
    font-size: 2.8rem

// Tablet Landscape (768px - 991px)
@media (max-width: 991px)
  .footer-container
    padding: 6rem 4rem
    flex-direction: column
    gap: 4rem
    text-align: center
  
  .footer-left
    align-items: center
  
  .footer-right
    width: 100%
    justify-content: center
  
  .contact-title
    font-size: 4rem
  
  .contact-description,
  .contact-email
    font-size: 2.5rem
  
  .footer-icon
    max-width: 300px

// Tablet Portrait (576px - 767px)
@media (max-width: 767px)
  .footer-container
    padding: 4rem 2rem
    gap: 3rem
  
  .contact-title
    font-size: 3.5rem
  
  .contact-description,
  .contact-email
    font-size: 2.2rem
  
  .social-icons
    gap: 1.2rem
  
  .social-icon
    width: 2.5rem
    height: 2.5rem
  
  .footer-icon
    max-width: 250px

// Mobile Large (480px - 575px)
@media (max-width: 575px)
  .footer-container
    padding: 3rem 1.5rem
    gap: 2.5rem
  
  .contact-title
    font-size: 3rem
  
  .contact-description,
  .contact-email
    font-size: 2rem
  
  .social-icons
    gap: 1rem
  
  .social-icon
    width: 2.2rem
    height: 2.2rem
  
  .footer-icon
    max-width: 200px

// Mobile Small (360px - 479px)
@media (max-width: 479px)
  .footer-container
    padding: 2.5rem 1rem
    gap: 2rem
  
  .contact-title
    font-size: 2.5rem
  
  .contact-description,
  .contact-email
    font-size: 1.8rem
  
  .social-icons
    gap: 0.8rem
    flex-wrap: wrap
    justify-content: center
  
  .social-icon
    width: 2rem
    height: 2rem
  
  .footer-icon
    max-width: 180px

// Mobile Extra Small (maksimal 359px)
@media (max-width: 359px)
  .footer-container
    padding: 2rem 0.8rem
    gap: 1.5rem
  
  .contact-title
    font-size: 2.2rem
  
  .contact-description,
  .contact-email
    font-size: 1.6rem
  
  .social-icons
    gap: 0.6rem
  
  .social-icon
    width: 1.8rem
    height: 1.8rem
  
  .footer-icon
    max-width: 150px
</style>
