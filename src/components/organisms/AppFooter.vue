<script setup lang="ts"></script>

<template>
  <footer>
    <ul class="footer-list">
      <li>
        <div>
          <p>Volg ons op sociale media!</p>
          <p class="long">Neem een kijkje achter de schermen en blijf op de hoogte.</p>

          <div class="social-btns">
            <a
              href="https://www.instagram.com/barfish.nl/"
              target="_blank"
              aria-label="Our instagram"
            >
              <img src="/src/assets/insta-logo.svg" alt="instagram" />
            </a>

            <a
              href="https://www.facebook.com/profile.php?id=61572364054383"
              target="_blank"
              aria-label="Our facebok"
            >
              <img src="/src/assets/facebook-logo.svg" alt="facebook" />
            </a>

            <a href="https://tiktok.com" target="_blank" aria-label="Our tiktok">
              <img src="/src/assets/tiktok-log.svg" alt="tiktok" />
            </a>
          </div>
        </div>
      </li>
      <li>
        <div>
          <p>Bar Fish</p>
          <p>Kamperland</p>
        </div>
      </li>
      <li>
        <div>
          <p>Telefoonnummer: <span class="text-light">+31 58 648 4862</span></p>
          <p>Email: <span class="text-light">info@leforel.nl</span></p>
          <!--<p>Openingstijden: <span class="text-light">MA - ZO 18:00</span></p>-->
        </div>
      </li>
    </ul>
  </footer>
</template>

<style lang="css" scoped>
.footer-list {
  display: flex;
  flex-flow: row;
  justify-content: space-around;
  list-style-type: none;
  text-transform: uppercase;
  background-color: var(--footer-bg);
  color: var(--text-color-light);
  margin: 0 1rem;
  padding: 3rem 0;

  .long {
    font-size: small;
    font-weight: 300;
  }

  .social-btns {
    display: flex;
    flex-flow: row;
    gap: 0.5rem;
    margin-top: 1rem;

    & a {
      display: flex;
      flex-flow: column;
      padding: 0.5rem;
      background-color: var(--btn-color);
      border-radius: 50px;

      img {
        width: 1.5rem;
      }

      &:hover {
        transform: scale(1.1);
      }
    }
  }

  li {
    display: flex;
    flex-flow: column;
    justify-content: space-between;
    gap: 0.3rem;
    flex: 1;

    > div {
      margin: auto;
    }

    .text-light {
      font-weight: 300;
      margin-left: 0.5rem;
    }
  }
}

@media (max-width: 50rem) {
  .footer-list {
    flex-flow: column;
    justify-content: space-between;
    align-items: center;
    gap: 2.5rem;
    padding: 3rem 0.5rem;

    .social-btns {
      align-items: center;
      justify-content: center;
    }

    li {
      text-align: center;
    }
  }
}
</style>
