<script>
    let currentSelection = "simple";
</script>

<div class="tabs">
    <div
        on:click={() => (currentSelection = "simple")}
        on:keydown={() => (currentSelection = "simple")}
        class="simple feature"
        class:selected={currentSelection == "simple"}
    >
        Simple Bookmark
        <span class="selected-bottom" />
    </div>
    <div
        on:click={() => (currentSelection = "speedy")}
        on:keydown={() => (currentSelection = "speedy")}
        class="speedy feature"
        class:selected={currentSelection == "speedy"}
    >
        Speedy Searching
        <span class="selected-bottom" />
    </div>
    <div
        on:click={() => (currentSelection = "easy")}
        on:keydown={() => (currentSelection = "easy")}
        class="easy feature"
        class:selected={currentSelection == 'easy'}
    >
        Easy Sharing
        <span class="selected-bottom" />
    </div>
</div>

<div class="content" >
    <div class="simple-content" class:selected={currentSelection == 'simple'}>
        <img src="/illustration-features-tab-1.svg" alt="illustration of a tablet" />
        <h2>Bookmark in one click</h2>
        <p>
            Organize your bookmarks however you like. Our simple drag-and-drop interface gives you complete control over how you manage your favourite sites.
        </p>
    </div>
    <div class="speedy-content" class:selected={currentSelection == 'speedy'}>
        <img src="/illustration-features-tab-2.svg" alt="illustration of a tablet" />
        <h2>Intelligent search</h2>
        <p>
            Our powerful search feature will help you find saved sites in no time at all. No need to trawl through all of your bookmarks.
        </p>
    </div>
    <div class="easy-content" class:selected={currentSelection == 'easy'}>
        <img src="/illustration-features-tab-3.svg" alt="illustration of a tablet" />
        <h2>Share your bookmarks</h2>
        <p>
            Easily share your bookmarks and collections with others. Create a shareable link that you can send at the click of a button.
        </p>
    </div>
</div>

<style type="text/scss" lang="scss">
    @import "./vars.scss";

    .tabs{
        .feature {
            justify-content: center;
            height: 50px;
            border-bottom: 1px solid $grayish-blue;
            display: flex;
            flex-direction: column;
            align-items: center;
            position: relative;
            color: $grayish-blue;
        }
    
        .feature.simple {
            border-top: 1px solid $grayish-blue;
        }
    
        .selected {
            color: black;
            .selected-bottom {
                position: absolute;
                background-color: $soft-red;
                width: 30%;
                height: 5px;
                display: block;
                bottom: 0;
            }
        }
    }

    .content {
        margin-top: 4rem;
        margin-bottom: 5rem;

        .selected {
            display: flex !important;
        }

        .speedy-content,
        .easy-content,
        .simple-content {
            display: none;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            img {
                width: 90%;
            }
            h2 {
                margin-top: 2rem;
                margin-bottom: .5rem;
            }
            p {
                margin-bottom: 2rem;
                margin-top: 0;
                color: $grayish-blue;
                padding: 0 1.5rem;
            }
        }

    }

</style>
