<script>
    import logo from '../assets/images/logo.svg';
    import close from '../assets/images/icon-menu-close.svg';
    import hamburger from '../assets/images/icon-menu.svg';

    let isOpen = false;

    function toggleMenu() {
        isOpen = !isOpen;
    }
</script>

<header class="container">
    <a href="#">
        <img class="logo" src={logo} alt="logo">
    </a>
    <button class="hamburger" on:click={toggleMenu}>
        <img src={hamburger} alt="hamburger">
    </button>
    <div class="overlay" class:show={isOpen}></div>
    <nav class:show={isOpen}>
        <button on:click={toggleMenu}>
            <img src={close} alt="close">
        </button>

        <a href="home">home</a>
        <a href="new">new</a>
        <a href="popular">popular</a>
        <a href="trending">trending</a>
        <a href="categories">categories</a>
    </nav>
</header>

<style lang="scss">
    header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 2rem .5rem;
        margin-top: 3.5rem;
        margin-bottom: 1rem;
    }

    .logo {
        width: 4rem;
    }

    // remove button styles
    button {
        background: none;
        border: none;
        cursor: pointer;
    }

    .hamburger {
        display: none;
    }

    nav {
        font-size: 1.1rem;

        button {
            display: none;
        }

        a {
            text-decoration: none;
            color: var(--dark-gray);
            text-transform: capitalize;

            padding: .5rem .8rem;
            transition: color .2s ease-out;

            &:hover {
                color: var(--primary-red);
            }
        }
    }

    .overlay {
        z-index: 1;
        position: fixed;
        width: 100vw;
        height: 100vh;
        inset: 0;
        background-color: var(--black);
        opacity: .5;
        display: none;

        &.show {
            display: block;
        }
    }

    @media screen and (max-width: 576px) {
        header {
            margin-top: 0;
            margin-bottom: .5rem;
        }
        .logo {
            width: 3rem;
        }

        .hamburger {
            display: block;

            img {
                width: 2.5rem;
            }
        }

        nav {
            position:fixed;
            z-index: 2;
            width: 70vw;
            height: 100vh;
            top: 0;
            right: -70vw;
            background-color: white;
            display: flex;
            flex-direction: column;
            align-items: start;
            padding-top: 20vh;
            transition: right .2s ease-out;

            button {
                display: block;
                position: absolute;
                top: 0;
                right: 0;
                padding-top: 1.5rem;
                padding-right: 1.2rem;
                
                img {
                    width: 2rem;
                }
            }
            
            a {
                color: var(--black);
                padding: .8rem 1.5rem;
            }

            &.show {
                right: 0;
            }
        }
    }
</style>