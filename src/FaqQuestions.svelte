<script>
    import { slide } from "svelte/transition";
    export let entry;
    let isOpen = false;
    const toggle = () => (isOpen = !isOpen);
</script>


<div class="container">
    <button on:click={toggle} aria-expanded={isOpen}
        >
        {entry[0]}
        <svg xmlns="http://www.w3.org/2000/svg" width="18" height="12"
            ><path
                fill="none"
                stroke="currentcolor"
                stroke-width="3"
                d="M1 1l8 8 8-8"
            />
        </svg>
    </button>
    {#if isOpen}
        <div transition:slide={{ duration: 300 }}>
            <p class="content">{entry[1]}</p>
        </div>
    {/if}
</div>


<style lang="scss">
    @import "./vars.scss";

    .container {
        border-bottom: 1px solid $grayish-blue;
        width: 90%;
        margin: 0 auto;
    }

    button {
        width: 100%;
        border: none;
        background: none;
        display: flex;
        align-items: center;
        justify-content: space-between;
        color: black;
        font-size: 1rem;
        cursor: pointer;
        padding: 1.5rem 0;
        text-align: left;
        border-radius: 0;

        &:focus {
            outline: none;
        }
    }

    .content {
        color: $grayish-blue;
        text-align: left;
        width: 100%;
        margin: 0;
        padding-bottom: 1.5rem;
    }

    svg {
        color: $soft-blue;
        transition: transform 0.2s ease-in;
    }

    [aria-expanded="true"] svg {
        transform: rotate(0.5turn);
        color: $soft-red;
    }
</style>
