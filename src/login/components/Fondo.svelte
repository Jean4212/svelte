<script>
  import { onMount } from "svelte";
    
  const images = ["image1.jpg", "image2.jpg", "image3.jpg", "image4.jpg"];  
  images.sort(() => Math.random() - 0.5);

  let imageIndex = 0;

  

  onMount(() => {
    const interval = setInterval(() => {
      imageIndex = (imageIndex + 1) % images.length;
    }, 10000);

    return () => {
      clearInterval(interval);
    };
  });
</script>

<div class="slider-container">
  {#each images as image, i}
    <img
      class="slider-image {i === imageIndex ? 'active' : ''}"
      src={image}
      alt=""      
    />
  {/each}
</div>

<style>
  .slider-container {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    z-index: -1;
    overflow: hidden;
  }

  .slider-image {
    position: absolute;
    top: 0;
    height: 100%;
    width: 100%;
    object-fit: cover;
    opacity: 0;
    transition: opacity 0.5s;
  }

  .slider-image.active {
    opacity: 1;
  }
</style>
