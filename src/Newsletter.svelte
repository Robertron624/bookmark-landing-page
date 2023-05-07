<script>

    let email = '';
    let inputError = false;

    const validateEmail = (email) => {
        const re = /\S+@\S+\.\S+/;
        return re.test(email);
    }

    function handleSubmit(e) {
        e.preventDefault();

        if (!validateEmail(email)) {
            inputError = true;
            return;
        }
        inputError = false;

        alert(`Email: ${email} submitted!`);
    }

</script>

<div class="container">
    <span>
        35,000+ already joined
    </span>
    <h2>
        Stay up-to-date with what we're doing
    </h2>
    <form on:submit={handleSubmit} action="POST">
        <div class="email-and-error">
            <input class:input-error="{inputError == true}" bind:value={email} type="email" placeholder="Enter your email address" />
            {#if inputError}
                <span class="error">Whoops, make sure it's an email</span>
                <img src="/icon-error.svg" alt="exclamation icon" class="error-icon">
            {/if}
        </div>
        <button type="submit">Contact Us</button>
    </form>
</div>

<style lang="scss">

    @import "./vars.scss";

    .container {
        background-color: $soft-blue;
        color: white;
        padding: 4rem 2rem;

        & > span {
            font-size: 1rem;
            font-weight: 500;
            text-transform: uppercase;
            opacity: 0.7;
        }

        h2 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            margin-top: .3rem;
            @include desktop {
                font-size: 2rem;
                margin-bottom: 2.5rem;
                padding: 0 28rem;
            }
        }

        form {
            display: flex;
            gap: 1rem;
            flex-direction: column;
            max-width: 40rem;
            margin: 0 auto;
            
            @include desktop {
                flex-direction: row;
                gap: 2rem;
                justify-content: center;
            }

            button,
            input {
                height: 50px;
                border-radius: 5px;
                border: none;
            }

            .email-and-error {
                position: relative;
                @include desktop {
                    width: 50%;
                }
                input {
                    padding: 0 1rem;
                    width: 90%;
    
                    &::placeholder {
                        font-weight: 600;
                        opacity: 0.4;
                    }

                    &.input-error {
                        outline: 2px solid $soft-red;
                        border-radius: 5px;
                    }
                }

                .error {
                    font-size: 0.7rem;
                    color: white;
                    font-weight: 500;
                    text-align: left;
                    font-style: italic;
                    display: inherit;
                    background-color: $soft-red;
                    padding: .5rem .7rem;
                    border-radius:0 0 5px 5px;
                    outline: 2px solid $soft-red;
                }

                .error-icon {
                    position: absolute;
                    right: 0;
                    top: 15px;
                    margin: auto;
                    padding: 0 1rem;
                }
            }


            button {
                background-color: $soft-red;
                color: white;
                font-weight: 500;
                cursor: pointer;
                border: 2px solid $soft-red;
                transition: all 0.3s ease-in-out;

                &:hover {
                    background-color: white;
                    color: $soft-red;
                }
            }
        }
    }

</style>