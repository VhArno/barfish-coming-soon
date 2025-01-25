<script setup lang="ts">
import AppButton from '@/components/atoms/AppButton.vue'
import AppInput from '@/components/molecules/AppInput.vue'
import VueCountdown from '@chenfengyuan/vue-countdown'
import { ref, computed } from 'vue'

// Target countdown date: March 1st, 2025
const countdownDate = ref(new Date(2025, 2, 1))

const countdownTime = computed(() => {
  const now = new Date().getTime()
  const target = countdownDate.value.getTime()
  return Math.max(target - now, 0)
})

const submitEmailAddress = async () => {
  console.log('Email added')
}
</script>

<template>
  <section class="container">
    <div class="intro">
      <div class="intro-text">
        <h1>BAR FISH: Binnenkort in Kamperland!</h1>

        <div>
          <p>
            We zijn druk bezig met de voorbereidingen van BAR FISH, een nieuw klein en gastvrij
            buurtrestaurant waar lokale en verse producten uit onze regio centraal staan. Vanaf
            begin maart kun je bij BAR FISH genieten van zorgvuldig bereide gerechten, een sterke
            selectie bijpassende wijnen en een ontspannen sfeer.
          </p>

          <p>
            Onze menukaart is nog in ontwikkeling, maar we kunnen alvast beloven dat deze een mix
            zal bieden van traditionele visgerechten waar je je vingers bij aflikt. ✨
          </p>
        </div>

        <vue-countdown :time="countdownTime" v-slot="{ days, hours, minutes, seconds }">
          <div class="countdown-grid">
            <div class="countdown-item">
              <h3>{{ days }}</h3>
              <span>Dagen</span>
            </div>

            <span>:</span>

            <div class="countdown-item">
              <h3>{{ hours }}</h3>
              <span>Uren</span>
            </div>

            <span>:</span>

            <div class="countdown-item">
              <h3>{{ minutes }}</h3>
              <span>Minuten</span>
            </div>

            <span>:</span>

            <div class="countdown-item">
              <h3>{{ seconds }}</h3>
              <span>Seconden</span>
            </div>
          </div>
        </vue-countdown>
      </div>
    </div>

    <div class="contact">
      <div class="contact-text">
        <h2>Wil je niets missen?</h2>
        <p>
          Laat je e-mailadres achter en blijf op de hoogte van onze opening en het laatste nieuws!
        </p>

        <form @submit.prevent="submitEmailAddress">
          <AppInput class="input" label="Email adress" type="email" autocomplete="email"></AppInput>

          <AppButton>Verstuur</AppButton>
        </form>

        <h3>We kijken ernaar uit om je vanaf maart te verwelkomen bij BAR FISH!</h3>
      </div>
    </div>
  </section>
</template>

<style lang="css" scoped>
.container {
  .intro {
    position: relative;
    background-image: url('/src/assets/bg-seafood.jpg');
    background-repeat: no-repeat;
    background-size: cover;
    background-color: transparent;
    min-height: 40rem;
    display: flex;
    align-items: center;
    border-radius: 50px;
    margin: 1rem;

    &::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(19, 9, 0, 0.521);
      z-index: 1;
      border-radius: 50px;
    }

    .intro-text {
      display: flex;
      flex-flow: column;
      gap: 1.5rem;
      position: relative;
      z-index: 2;
      width: 50%;
      margin: 0 4rem;

      h1 {
        font-size: 3rem;
      }

      p {
        font-size: 1.1rem;
        margin-bottom: 1rem;
      }

      .countdown-grid {
        display: flex;
        flex-flow: row;
        gap: 1rem;
        align-items: center;
      }

      .countdown-item {
        text-align: center;
        margin: 0 1rem;

        h3 {
          font-size: 2rem;
          margin: 1rem 0;
        }

        span {
          font-weight: 300;
        }
      }
    }
  }

  .contact {
    text-align: center;
    padding: 2rem;
    background-color: var(--accent2);
    width: 50%;
    margin: auto;
    margin-top: 3rem;
    border-radius: 10px;
    transform: rotate(1deg);

    .contact-text {
      transform: rotate(-1deg);
    }

    form {
      flex: 1;
      margin-top: 3rem;

      .input {
        width: 60%;
        margin: auto;
      }

      button {
        margin-top: 1rem;
      }
    }
  }
}

@media (max-width: 48rem) {
  .container {
    .intro {
      margin: 0rem;
      border-radius: 0px;

      &::before {
        border-radius: 0px;
      }

      .intro-text {
        width: 85%;
        margin: 1rem auto;

        .countdown-grid {
          display: flex;
          flex-flow: row wrap;
        }

        .countdown-item {
          width: 30%;
          text-align: center;
          margin: 0;

          h3 {
            font-size: 1.5rem;
            margin: 1rem 0;
          }

          span {
            font-weight: 300;
          }
        }
      }
    }

    .contact {
      text-align: center;
      padding: 2rem;
      background-color: var(--accent2);
      transform: rotate(0deg);
      width: 70%;

      .contact-text {
        transform: rotate(0deg);
      }

      form {
        margin-top: 3rem;

        .input {
          width: 100%;
          margin: auto;
        }

        button {
          margin-top: 1rem;
        }
      }
    }
  }
}
</style>
