<script>
    import web3 from '../assets/images/image-web-3-desktop.jpg';
</script>

<main>
    <img src={web3} alt="web 3">
    <h1>The Bright Future of Web 3.0?</h1>
    <p>We dive into the next evolution of the web that claims to put the power of the platforms back into the hands of the people. But is it really fulfilling its promise?<a href="#read-more">Read more</a></p>
</main>

<style lang="scss">
    main {
        display: grid;
        grid-template-columns: auto auto;
        row-gap: 2rem;
        column-gap: 3rem;

        img {
            width: 100%;
            object-fit: cover;
            grid-column: 1 / 3;
        }

        h1 {
            font-weight: 800;
            font-size: 3.5rem;
            margin: 0;
            line-height: 100%;
        }

        p {
            line-height: 1.7rem;
            color: var(--dark-gray);

            display: flex;
            flex-direction: column;
            justify-content: space-between;
            align-items: start;
        }

        a {
            display: block;
            width: fit-content;
            text-transform: capitalize;
            text-decoration: none;
            color: var(--white);
            background-color: var(--primary-red);
            padding: .7rem 2.2rem;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 5px;
            font-size: 0.85rem;
            transition: background-color 0.2s ease-out;
            margin-top: 2rem;

            &:hover {
                background-color: var(--black);
            }
        }
    }

    @media screen and (min-width: 576px) {
        main {
            grid-auto-rows: max-content;
        }
        p {
            margin: 0;
        }
    }

    @media screen and (max-width: 576px) {
        main {
            grid-template-columns: auto;
            row-gap: 0;
            margin-bottom: 1.5rem;

            img {
                aspect-ratio: 1 / 1;
                grid-column: 1 / 2;
            }

            h1 {
                font-size: 2.6rem;
                margin: 2rem 0 0 0;
            }

            p {
                display: block;
            }
            
            a {
                margin: 1rem 0;
            }
        }
    }
</style>