<script>
  import { onMount } from 'svelte';
  import AOS from 'aos';
  import 'aos/dist/aos.css';
  import { gsap } from 'gsap';

  onMount(() => {
    AOS.init({
      duration: 800,
      easing: 'ease-in-out',
      once: false
    });

    gsap.to('.intro', { opacity: 1, duration: 1.5 });
  });
</script>

<!-- 3D Animated Card -->
<div class="card3d-container">
  <div class="card3d" data-aos="zoom-in">
    <div class="card3d-content">
      <div class="card3d-text">
        <h1 class="title">S.K.S</h1>
        <p>Welcome to Sanjay Kirana Store.</p>
      </div>
      <img
        src="https://images.pexels.com/photos/264636/pexels-photo-264636.jpeg"
        alt="SKS Logo"
        class="card3d-img"
      />
    </div>
  </div>
</div>

<!-- Scroll-based Section -->
<section class="card bg-dark" data-aos="fade-right">
  <div>
    <h1 class="title text-white">Features</h1>
    <p class="text text-white">The SKS will give you the best quality groceries.</p>
    <p class="text text-white">The SKS also have a unique products.</p>
    <p class="text text-white">The Sks Will Also Affiliates Valdilal Icecream.</p>
  </div>
  <img
    src="https://images.pexels.com/photos/1813504/pexels-photo-1813504.jpeg"
    alt="detail"
    height="200"
    width="200"
  />
</section>

<style>
  :global(body) {
    background: linear-gradient(to right, #000428, #004e92);
    margin: 0;
    font-family: 'Segoe UI', sans-serif;
  }

  .card3d-container {
    display: flex;
    justify-content: center;
    padding: 2rem;
    perspective: 1000px;
  }

  .card3d {
    width: 90%;
    max-width: 800px;
    background: #ffffff10;
    border-radius: 20px;
    overflow: hidden;
    transition: transform 0.4s ease, box-shadow 0.3s ease;
    transform-style: preserve-3d;
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
  }

  .card3d:hover {
    transform: rotateY(5deg) rotateX(5deg) scale(1.02);
    box-shadow: 0 15px 35px rgba(0, 0, 0, 0.5);
  }

  .card3d-content {
    display: flex;
    align-items: center;
    padding: 2rem;
    backdrop-filter: blur(8px);
  }

  .card3d-text {
    flex: 1;
    padding-right: 1.5rem;
    color: white;
  }

  .card3d-text .title {
    font-size: 2rem;
    margin-bottom: 0.5rem;
    color: #fff;
  }

  .card3d-text p {
    font-size: 1.1rem;
    color: #eee;
  }

  .card3d-img {
    width: 200px;
    height: 200px;
    object-fit: cover;
    border-radius: 1rem;
    box-shadow: 0 5px 15px rgba(255, 255, 255, 0.2);
  }

  .card.bg-dark {
    display: flex;
    justify-content: space-between;
    padding: 2rem;
    margin: 2rem;
    border-radius: 1rem;
    background-color: rgba(0, 0, 0, 0.3);
    backdrop-filter: blur(5px);
  }

  .title {
    font-size: 2rem;
    font-weight: bold;
  }

  .text {
    font-size: 1.1rem;
    margin: 0.5rem 0;
  }

  .text-white {
    color: white;
  }

  .intro {
    opacity: 0;
  }
</style>
