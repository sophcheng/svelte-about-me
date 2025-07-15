<!-- src/lib/Expander.svelte -->

<!-- <script>
    export let image; // Image URL prop
    export let title; // Title prop
    export let description; // Description prop

    document.addEventListener("DOMContentLoaded", function () {
        const expanders = document.querySelectorAll(".expander");

        expanders.forEach((header) => {
            header.addEventListener("click", () => {
                const accordionItem = header.closest(".expander-item");
                const accordionContent =
                    accordionItem.querySelector(".expander-content");
                const icon = header.querySelector(".icon");

                accordionItem.classList.toggle("open");
                const isExpanded = accordionItem.classList.contains("open");

                header.setAttribute("aria-expanded", isExpanded.toString());
                accordionContent.setAttribute(
                    "aria-hidden",
                    (!isExpanded).toString(),
                );

                if (icon) {
                    icon.textContent = isExpanded ? "-" : "+";
                }
            });
        });
    });
</script> -->

<script>
    export let image;
    export let title;
    export let description;

    let open = false;

    function toggle() {
        open = !open;
    }
</script>

<!-- <div class="expander-item">
    <img src={image} alt={title} />
    <h2 class="expander">
        {title}
        <span class="icon">+</span>
    </h2>
    <div class="expander-content">
        <p>{description}</p>
    </div>
</div> -->

<div class="expander-item {open ? 'open' : ''}">
    <div>
        <img src={image} alt={title} />
        <button class="expander" on:click={toggle} aria-expanded={open}>
            {title}
            <span class="icon">{open ? "-" : "+"}</span>
        </button>
    </div>
    {#if open}
        <div class="expander-content" aria-hidden={!open}>
            <p>{description}</p>
        </div>
    {/if}
</div>

<style>
    img {
        width: 200px;
        height: auto;
        padding: 10px;
        border-style: double;
        border-radius: 25px;
    }
    button:hover {
        background-color: white;
        color: #535bf2;
        text-transform: uppercase;
        transition-property: inherit;
    }
    button:active {
        background-color: #535bf2;
        color: white;
        text-transform: uppercase;
        transform: translateY(6px);
    }

    .expander-content {
        display: none;
    }
    .expander {
        cursor: pointer;
    }
    .expander-item.open .expander-content {
        display: flex;
        flex-direction: column;
        flex-wrap: wrap;
        align-self: center;
        border-style: groove;
        border-radius: 20px;
        background-color: white;
        width: 200px;
    }
    .expander-item {
        padding: 20px;
        display: flex;
        flex-direction: column;

        display: flex;
        justify-content: center;
        border-style: groove;
        background-color: black;
        color: #844979;
        border-radius: 20px;
        width: 300px;
        margin: 20px;
    }

    .expander .icon {
        font-family: "Lucida Console", "monospace";
    }
</style>
