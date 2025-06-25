<script>
  let card;
  let xRotation = 0;
  let yRotation = 0;

  const handleMouseMove = (e) => {
    const rect = card.getBoundingClientRect();
    const x = e.clientX - rect.left;
    const y = e.clientY - rect.top;

    const centerX = rect.width / 2;
    const centerY = rect.height / 2;

    xRotation = ((y - centerY) / centerY) * 10;
    yRotation = ((x - centerX) / centerX) * 10;
  };

  const resetRotation = () => {
    xRotation = 0;
    yRotation = 0;
  };
</script>

<style>
  .card-3d {
    perspective: 1000px;
  }
  .inner {
    transition: transform 0.2s ease;
    transform-style: preserve-3d;
    will-change: transform;
  }
</style>

<div class="card-3d w-[300px] h-[400px] mx-auto" on:mousemove={handleMouseMove} on:mouseleave={resetRotation}>
  <div
    bind:this={card}
    class="inner bg-white rounded-2xl shadow-xl w-full h-full p-6"
    style="transform: rotateX({-xRotation}deg) rotateY({yRotation}deg);"
  >
    <h2 class="text-xl font-bold mb-2">3D Card</h2>
    <p class="text-gray-600">Interactive 3D card using SvelteKit</p>
  </div>
</div>
