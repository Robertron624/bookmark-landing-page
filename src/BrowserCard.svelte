<script>
    export let name;
    export let version;
    export let url;
</script>

<div class="card">
    <img src={url} alt={`${name} logo`} />
    <div class="text">
        <h3>Add to {name}</h3>
        <p>Minimum version {version}</p>
    </div>
    <button> Add & Install Extension </button>
</div>

<style lang="scss">
    @import "./vars.scss";

    .card {
        background-color: white;
        border-radius: 5px;
        padding: 2rem 0;
        margin-bottom: 2rem;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        transition: all 0.2s ease-in-out;
        width: 90%;

        @include desktop {
            max-width: 20rem;

            &:nth-of-type(2) {
                margin-top: 6rem;
            }

            &:nth-of-type(3) {
                margin-top: 12rem;
            }
        }

        &:hover {
            transform: translateY(-5px);
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
        }
    }

    .text {
        padding-bottom: 3rem;

        background-image: url("/bg-dots.svg");
        background-position: bottom;
        background-repeat: repeat-x;

        h3 {
            margin-bottom: 1rem;
        }

        p {
            margin: 0;
            color: $grayish-blue;
        }
    }

    button {
        margin-top: 2rem;
        background-color: $soft-blue;
        color: white;
        border-radius: 5px;
        padding: 1rem 2rem;
        font-weight: 500;
        font-size: 1rem;
        cursor: pointer;
        transition: all 0.3s ease-in-out;
        box-shadow: 0 0 10px $soft-blue;
        border: 2px solid $soft-blue;

        &:hover {
            background-color: white;
            color: $soft-blue;
        }
    }
</style>
