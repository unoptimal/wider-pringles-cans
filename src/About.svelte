<script>
  export let show = false;
  export let onClose;
</script>

{#if show}
<div class="modal">
    <div class="modal-content">
        <div class="modal-columns">

            <!-- Left Column -->
            <div class="left-column">
                <!-- Banner and Title -->
                <div class="top-content">
                    <img class="logo" src="../src/assets/desktop.svg" alt="Wider Pringles Logo">
                </div>
                <!-- Description for Mobile -->
                <div class="description mobile-desc">
                    <p>A 10" x 5" x 5" can. Your hand is almost guaranteed to fit.</p>
                    <p>Unfortunately, this project is not affiliated with Pringles or Kellog's in any way.</p>
                    <small>by <a href='https://unoptimal.com/' target='_blank'>unoptimal</a></small>
                    <br>
                    <button class="close-button" on:click={onClose}>Close</button>
                </div>
            </div>

            <!-- Right Column for Images -->
            <div class="right-column">
                <div class="image" style="background-image: url('../src/assets/three.webp')"></div>
                <div class="image" style="background-image: url('../src/assets/in.webp')"></div>
                <div class="image" style="background-image: url('../src/assets/compare.webp')"></div>
            </div>  

            <!-- Description for Desktop -->
            <div class="description desktop-desc">
                <p>A 10" x 5" x 5" can. Your hand is almost guaranteed to fit.</p>
                <p>Unfortunately, this project is not affiliated with Pringles or Kellog's in any way.</p>
                <small>by <a href='https://unoptimal.com/' target='_blank'>unoptimal</a></small>
                <br>
                <button class="close-button" on:click={onClose}>Close</button>
            </div>
        </div>
    </div>
</div>
{/if}

<style>
p {
    font-size: 1.5rem;
}

.modal {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    background: rgba(0, 0, 0, 0.7);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 20;
}

.modal-content {
    background: white;
    padding: 20px;
    border-radius: 10px;
    max-width: 1000px;
    width: 90%;
    height: 75%;
    display: flex;
    flex-direction: column;
}

.modal-columns {
    flex: 1;
    display: flex;
    gap: 20px;
    width: 100%;
    flex-direction: row; 
}

.top-content {
    text-align: center;
}

.left-column, .right-column {
    flex: 1;
}

.left-column {
    flex: 1;
    display: flex;
    flex-direction: column;

}

.logo {
    max-width: 100%;
    height: auto;
}

.right-column {
    display: flex;
    flex-direction: column;
    gap: 20px;
    overflow-y: auto;
    overflow-x: hidden; 
    max-height: 60%; 
}

.image {
    min-height: 300px;
    min-width: 300px;
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
}

.close-button {
    background-color: #f1f1f1;
    border: none;
    cursor: pointer;
    transition: background-color 0.3s;
}

.close-button:hover {
    background-color: #ddd;
}

.desktop-desc {
    display: none;
}

@media (max-width: 768px) {

  .left-column, .right-column {
        flex: none; 
    }

  p {
        font-size: 1.25rem;
    }

    .modal-content {
        height: 85%;
        width: 85%;
    }

    .modal-columns {
        flex-direction: column;
    }

    .right-column {
        display: flex;
        flex-direction: row;
        overflow-x: auto;
        gap: 10px;
        white-space: nowrap;
    }

    .image {
        flex: 0 0 auto;
        width: 100%;
        max-width: 400px;
        height: auto;
        min-height: 250px;
        background-size: contain;
        overflow-x: hidden;
    }

    .desktop-desc {
        display: block;
    }

    .mobile-desc {
        display: none;
    }
}
</style>
