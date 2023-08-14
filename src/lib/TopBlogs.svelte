<script lang="ts">
    import retro from '../assets/images/image-retro-pcs.jpg';
    import laptops from '../assets/images/image-top-laptops.jpg';
    import gaming from '../assets/images/image-gaming-growth.jpg';

    interface TopBlog {
        image: string;
        caption: string;
        title: string;
        description: string;
        link: string;
    }

    const data: [TopBlog, TopBlog, TopBlog] = [
        {
            image: retro,
            caption: 'retro console',
            title: 'Reviving Retro PCs',
            description: 'What happens when old PCs are given modern upgrades?',
            link: '#',
        },
        {
            image: laptops,
            caption: 'laptop keyboard',
            title: 'Top 10 Laptops of 2022',
            description: 'Our best picks for various needs and budgets.',
            link: '#',
        },
        {
            image: gaming,
            caption: 'gaming controller',
            title: 'The Growth of Gaming',
            description: 'How the pandemic has sparked fresh opportunities.',
            link: '#',
        }
    ];

</script>

<aside>
    <ul>
        {#each data as blog, idx}
            <li>
                <img src={blog.image} alt={blog.caption}>
                <div>
                    <h1>{'0' + (idx + 1)}</h1>
                    <a href={blog.link}>{blog.title}</a>
                    <p>{blog.description}</p>
                </div>
            </li>
        {/each}
    </ul>
</aside>

<style lang="scss">
    aside {
        margin: 3rem 0;

        ul {
            padding: 0;
            list-style-type: none;
            display: flex;

            li {
                display: grid;
                grid-template-columns: 1fr 3fr;
                gap: 1rem;

                img {
                    width: 100%;
                    margin: auto 0;
                }

                div {
                    display: flex;
                    flex-direction: column;
                    justify-content: space-between;
                    * {
                        margin: .2rem 0;
                    }
                }

                h1 {
                    color: var(--gray);
                    font-size: 2rem;
                }

                a {
                    text-decoration: none;
                    font-size: 1.2rem;
                    font-weight: 700;
                    color: var(--black);
                    transition: color .2s;

                    &:hover {
                        color: var(--primary-red);
                    }
                }

                p {
                    line-height: 150%;
                    color: var(--dark-gray);
                }
            }
        }
    }

    @media screen and (max-width: 576px) {
        aside {
            ul {
                display: block;
            }
        }
    }
</style>