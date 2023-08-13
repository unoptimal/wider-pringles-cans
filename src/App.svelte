<script>
  import About from "./About.svelte";

  let showAbout = false;
  function toggleAbout() {
      showAbout = !showAbout;
  }
</script>

<div class="container">
  <div class='more'>
      <button on:click={toggleAbout}>MORE</button>
      <About show={showAbout} onClose={toggleAbout} />
  </div>
  <div class="video-wrapper">
    <iframe src="https://www.youtube.com/embed/4TBWZnceI9o" title="Introducing: Wider Pringles Cans" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; margin: 0;"></iframe>
  </div>
</div>

<style>
  :global(body), :global(html) {
    
    margin: 0;
    padding: 0;
    height: 100%;
    background-size: cover; /* Make the image cover the entire element */
    background-repeat: no-repeat; /* Prevent the image from repeating */
    background-position: center center; /* Center the image */
    overflow: hidden;

  }

  :global(body) {
    background-image: url('../src/assets/BG.webp');
}


  /* Box-sizing reset */
  *, *:before, *:after {
    box-sizing: border-box;
  }

  .container {
    display: flex;
    flex-direction: column;
    justify-content: center; /* vertically centers content */
    align-items: center; /* horizontally centers content */
    height: auto;
    min-height: 100vh;
}

  .video-wrapper {
  position: absolute;
  top: 10%;       /* Adjust this value to position it vertically */
  right: 10%;     /* Adjust this value to position it horizontally */
  height: 40%;
  width: 40%;    /* Width of the video, can adjust based on design */
  padding-bottom: 16.875%;  /* This ensures a 16:9 ratio: 30% * 9/16 */
  overflow: hidden; 
  z-index: 10;
 
}

.video-wrapper iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border: none;
}

.more{
  position: absolute;
  top: 90%;
  left: 68%;
  padding-bottom: 16.875%;
  overflow: hidden;
}

  /* Mobile styles */
  @media (max-width: 768px) {
    :global(body) {
      background-image: url('../src/assets/MOBILEBG.webp');
    }

    .video-wrapper {
      top: 10%;  /* Adjust this value for mobile */
      right: 10%;  /* Adjust this value for mobile */
      height: 25%;  /* Adjust this value for mobile */
      width: 80%;  /* Adjust this value for mobile */
    }

    .more{
  position: absolute;
  top: 92.5%;
  left: 75%;
  padding-bottom: 16.875%;
  overflow: hidden;
}
  }
</style>


