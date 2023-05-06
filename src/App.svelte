<script>
  import svelteLogo from './assets/svelte.svg'
  import viteLogo from '/vite.svg'
  import Counter from './lib/Counter.svelte'
  import FeaturesTabs from './FeaturesTabs.svelte'
</script>

<header>
  <img src="/logo-bookmark.svg" alt="bookmark logo">
  <div class="mobile-menu">
    <img src="/icon-hamburger.svg" alt="hamburger icon">
  </div>
</header>

<main>
  <div class="hero">
    <div class="background-shape"></div>
    <img src="/illustration-hero.svg" alt="illustration of a tablet">
  </div>
  <section class="intro-text">
    <h1 class="title">
      A Simple Bookmark Manager
    </h1>
    <p>
      A clean and simple interface to organize your favourite websites. Open a new browser tab and see your sites load instantly. Try it for free.
    </p>
    <div class="buttons">
      <button>
        Get it on Chrome
      </button>
      <button>
        Get it on Firefox
      </button>
    </div>
  </section>
  <section class="features">
    <h1 class="title">
      Features
    </h1>
    <p class="content">
      Our aim is to make it quick and easy for you to access your favourite websites. Your bookmarks sync between your devices so you can access them on the go.
    </p>
    <FeaturesTabs />
  </section>
</main>

<style type="text/scss" lang="scss">

  @import './vars.scss';

  main {
    text-align: center;


    .hero {
      position: relative;
      margin-top: 5rem;

      .background-shape {
        z-index: -1;
        position: absolute;
        top: 40%;
        right: 0;
        width: 76%;
        height: 150px;
        background-color: $soft-blue;
        border-radius: 40% 0 0 40%;
      }

      img {
        width: 90%;
        z-index: 1;
      }
    }

    .intro-text {
      margin-top: 3rem;

      h1.title {
        margin-top: 3rem;
        font-size: 2rem;
        font-weight: 500;
        color: $very-dark-blue;
      }

      p{
        color: $grayish-blue;
        padding: 0 2rem;
      }

      .buttons 
      {
        margin-top: 2rem;
        margin-bottom: 2rem;
        display: flex;
        justify-content: center;
        gap: 1rem;

        button {
          // padding: 1rem 2rem;
          border-radius: 5px;
          border: none;
          font-weight: 500;
          cursor: pointer;
          transition: all 0.3s ease-in-out;
          color: white;
        }

        button:first-of-type {
          background-color: $soft-blue;
        }
        
        button:last-of-type {
          background-color: white;
          color: $grayish-blue;
          box-shadow: 1px 2px 7px 0px hsl(229, 8%, 60%);
        }
      }
    }

    section.features {
      margin-top: 7rem;

      h1.title {
        font-size: 2rem;
        font-weight: 500;
        color: $very-dark-blue;
      }

      p.content {
        color: $grayish-blue;
        padding: 0 2rem;
      }
    }
  }

  header {
    display: flex;
    justify-content: space-between;
    padding: 2rem 2rem;
  }
  

</style>
