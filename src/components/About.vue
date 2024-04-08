<template>
      <section class="site-banner">
            <div class="container">
                <div class="row">
                    <div class="col-lg-6 col-md-12 site-title">
                        <h3 class="title-text text-uppercase">Hey, I am Hiten👋</h3>
                        <h4 class="text-uppercase">I am a <span id="subheading">{{ typeValue }} <span class="blinking-cursor">|</span> <span class="cursor" :class="{ typing: typeStatus }">&nbsp;</span></span> </h4>
                        <hr>
                        <p>🔥 Passionate React/Next.js Developer with a drive for crafting dynamic web experiences and a proven track record of delivering high-quality solutions.</p>
                        <p data-aos="zoom-in" data-aos-duration="1500">🚀 With over 2 years of experience in the field, I am dedicated to pushing the boundaries of full-stack development, adept at building end-to-end web applications that captivate users.</p>
                        <p   v-motion="{
                          initial: {
                            y: 100,
                            opacity: 0
                          },
                          enter: {
                            y: 0,
                            opacity: 1
                          }
                        }">📚 I thrive on learning and staying at the forefront of technology trends, consistently expanding my skill set to incorporate new tools and methodologies seamlessly into my projects.</p>
                        <p   v-motion="{
                            initial: {
                              y: 100,
                              opacity: 0
                            },
                            enter: {
                              y: 0,
                              opacity: 1
                            }
                          }"
                        >
                          🔒 Proficient in ReactJs, Vue.js, and JavaScript, I am committed to developing secure web applications with impeccable coding standards, ensuring the highest level of quality and reliability.
                        </p>
                        <p   v-motion="{
                          initial: {
                            y: 100,
                            opacity: 0
                          },
                          enter: {
                            y: 0,
                            opacity: 1
                          }
                        }"
                        >
                          ⭐️ Whether it's front-end development, back-end work, or full-stack solutions, I am committed to delivering excellence in every aspect of web development.
                        </p>
                        <p><github-button href="https://github.com/1994Chang">Follow @1994Chang</github-button></p>
                        <hr>
                        <div class="social">
                            <a target="_blank" rel="noreferrer" href="https://github.com/1994Chang" class="social-link"><i
                                    class="fab fa-github"></i></a>
                            <a target="_blank" rel="noreferrer" href="https://www.linkedin.com/in/hiten-vadhaiya"
                                class="social-link"><i class="fab fa-linkedin"></i></a>
                            <!-- <a target="_blank" rel="noreferrer" href="https://twitter.com/gope_boni"
                                class="social-link"><i class="fab fa-twitter"></i></a> -->
                            <a href="mailto: hiten.vadhaiya1994@gmail.com" class="social-link"><i class="fas fa-envelope"></i></a>
                        </div>
                        <div class="site-buttons">
                            <div class="d-flex flex-row flex-wrap">
                                <!-- <button type="button" class="btn button primary-button mr-4 text-uppercase first-btn"><a
                                        href="https://drive.google.com/file/d/1xe3pfKmqHvVcV5l-hQPhlcp12dSEhP4g/view" target="_blank">RESUME &nbsp;<i
                                            class="fas fa-external-link-alt" aria-hidden="true"></i></a></button> -->
                                <button type="button" class="btn button secondary-button text-uppercase second-btn"><a
                                        href="mailto: hiten.vadhaiya1994@gmail.com">Hire Me</a></button>
                            </div>
                        </div>
                    </div>
                    <div class="col-lg-6 col-md-12 banner-image">
                      <Vue3Lottie :animationData="DeveloperJSON"  :speed="1" loop
                            autoplay />
                    </div>

                </div>
            </div>
        </section>
</template>

<script>
import { Vue3Lottie } from 'vue3-lottie'
import DeveloperJSON from '@/assets/developer.json'
import GithubButton from 'vue-github-button'
export default {
  name: 'AboutMe',
  components: {
    Vue3Lottie,
    GithubButton
  },
  data(){
    return {
      typeValue: "",
      typeStatus: false,
      displayTextArray: ['Web Developer', 'React Js Developer', 'Vue Js Developer', 'Freelancer'],
      typingSpeed: 100,
      erasingSpeed: 100,
      newTextDelay: 2000,
      displayTextArrayIndex: 0,
      charIndex: 0,
      DeveloperJSON
    }
  },
  created() {
   setTimeout(this.typeText, this.newTextDelay + 200);
},
  methods: {
    typeText() {
      if (this.charIndex < this.displayTextArray[this.displayTextArrayIndex].length) {
        if (!this.typeStatus) this.typeStatus = true;
        this.typeValue += this.displayTextArray[this.displayTextArrayIndex].charAt(
          this.charIndex
        );
        this.charIndex += 1;
        setTimeout(this.typeText, this.typingSpeed);
      } else {
        this.typeStatus = false;
        setTimeout(this.eraseText, this.newTextDelay);
      }
    },
    eraseText() {
      if (this.charIndex > 0) {
        if (!this.typeStatus) this.typeStatus = true;
        this.typeValue = this.displayTextArray[this.displayTextArrayIndex].substring(
          0,
          this.charIndex - 1
        );
        this.charIndex -= 1;
        setTimeout(this.eraseText, this.erasingSpeed);
      } else {
        this.typeStatus = false;
        this.displayTextArrayIndex += 1;
        if (this.displayTextArrayIndex >= this.displayTextArray.length)
          this.displayTextArrayIndex = 0;
        setTimeout(this.typeText, this.typingSpeed + 1000);
      }
    },
  },
}
</script>

<style scoped>
.blinking-cursor {
  color: #2c3e50;
  -webkit-animation: 1s blink step-end infinite;
  -moz-animation: 1s blink step-end infinite;
  -ms-animation: 1s blink step-end infinite;
  -o-animation: 1s blink step-end infinite;
  animation: 1s blink step-end infinite;
}
@keyframes blink {
  from,
  to {
    color: transparent;
  }
  50% {
    color: #2c3e50;
  }
}
@-moz-keyframes blink {
  from,
  to {
    color: transparent;
  }
  50% {
    color: #2c3e50;
  }
}
@-webkit-keyframes blink {
  from,
  to {
    color: transparent;
  }
  50% {
    color: #2c3e50;
  }
}
@-ms-keyframes blink {
  from,
  to {
    color: transparent;
  }
  50% {
    color: #2c3e50;
  }
}
@-o-keyframes blink {
  from,
  to {
    color: transparent;
  }
  50% {
    color: #2c3e50;
  }
}
</style>