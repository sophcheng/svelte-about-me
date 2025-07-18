<!-- src/lib/ImageCard.svelte -->

<script>
    export let image; // Image URL prop
    export let title; // Title prop
    export let description; // Description prop
    export let color; // Pin color
</script>

<div class="parent">
    <div style="background-color: {color};" class="pin"></div>
    <div class="clasp"></div>
    <div class="pin-back"></div>
    <div class="card">
        <div class="hole"></div>
        <img src={image} alt={title} />
        <div class="card-content">
            <h2 class="card-title">{title}</h2>
            <p class="card-description">{description}</p>
        </div>
    </div>
</div>

<style>
    .card {
        background-color: #fff;
        border: 2px solid #ddd;
        border-style: inset;
        border-radius: 10px;
        overflow: hidden;
        width: 200px;
        min-height: 400px;
        box-shadow: 5px 5px 100px rgba(0, 0, 0, 0.1);
        margin: 20px;
        text-align: center;
        position: relative;
    }
    .card:hover {
        color: #666;
        border-style: outset;
        transform: translatey(40px);
        transition: transform 0.4s ease-in-out;
    }
    .parent {
        position: relative;
    }

    .card img {
        margin-top: 30px;
        width: 100%;
        height: auto;
    }

    .card-content {
        padding: 5px;
    }

    .card-title {
        font-size: 1.5em;
        color: #333;
        margin: 0 0 10px 0;
    }

    .card-description {
        font-size: 1em;
        margin: 0;
    }

    .hole {
        width: 30px;
        height: 30px;
        background-color: #844979;
        box-shadow: 5px 5px 100px rgba(0, 0, 0, 0.1);
        margin: 0 0 20px 0;
        justify-self: center;
        border-style: groove;
        border-radius: 15px;
        position: absolute;
        top: 15px;
        left: 115px;
        z-index: 1;
    }

    .clasp {
        width: 30px;
        height: 5px;
        background-color: silver;
        position: absolute;
        top: 5px;
        left: 135px;
        z-index: 3;
        border-style: none;
        border-radius: 5px;
    }
    .pin {
        width: 20px;
        height: 60px;
        top: -15px;
        left: 50px;
        background-color: lightseagreen;
        position: absolute;
        left: 139px;
        z-index: 2;
        border-style: outset;
        border-radius: 10px 10px 0 0;
        box-shadow: 5px 5px 100px rgba(0, 0, 0, 0.1);
    }
    .pin-back {
        width: 20px;
        height: 60px;
        background-color: darkcyan;
        position: absolute;
        top: -15px;
        left: 150px;
        z-index: 0;
        border-style: none;
        border-radius: 10px 10px 0 0;
    }
</style>
