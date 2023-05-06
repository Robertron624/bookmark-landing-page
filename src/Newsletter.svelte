<script>

</script>

<div class="container">
    <span>
        35,000+ already joined
    </span>
    <h2>
        Stay up-to-date with what we're doing
    </h2>
    <form action="POST">
        <input type="email" placeholder="Enter your email address" />
        <button type="submit">Contact Us</button>
    </form>
</div>

<style lang="scss">

    @import "./vars.scss";

    .container {
        background-color: $soft-blue;
        color: white;
        padding: 4rem 2rem;

        span {
            font-size: 1rem;
            font-weight: 500;
            text-transform: uppercase;
            opacity: 0.7;
        }

        h2 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            margin-top: .3rem;
        }

        form {
            display: flex;
            gap: 1rem;
            flex-direction: column;

            button,
            input {
                height: 50px;
                border-radius: 5px;
                border: none;
            }

            input {
                padding: 0 1rem;

                &::placeholder {
                    font-weight: 600;
                    opacity: 0.4;
                }
            }

            button {
                background-color: $soft-red;
                color: white;
                font-weight: 500;
                cursor: pointer;
                transition: all 0.3s ease-in-out;
            }
        }
    }

</style>