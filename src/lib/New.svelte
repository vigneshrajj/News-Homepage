<script lang="ts">
    interface Blog { 
        title: string; 
        description: string; 
        link: string; 
    }

    const data: [Blog, Blog, Blog] = [
        {
            title: 'Hydrogen VS Electric Cars',
            description: 'Will hydrogen-fueled cars ever catch up to EVs?',
            link: '#',
        },
        {
            title: 'The Downsides of AI Artistry',
            description: 'What are the possible adverse effects of on-demand AI image generation?',
            link: '#',
        },
        {
            title: 'Is VC Funding Drying Up?',
            description: 'Private funding by VC firms is down 50% YOY. We take a look at what that means.',
            link: '#',
        },
    ];
</script>

<aside>
    <h1>New</h1>
    <ul>
        {#each data as blog}
            <li>
                <a href={blog.link}>{blog.title}</a>
                <p>{blog.description}</p>
            </li>
        {/each}
    </ul>
</aside>

<style lang="scss">
    aside {
        background-color: var(--black);
        padding: 1.5rem;

        h1 {
            margin-top: 0;
            color: var(--primary-orange);
            font-size: 2.5rem;
        }

        ul {
            list-style-type: none;
            padding: 0;

            li {
                &:not(:last-child) {
                    padding-bottom: 1rem;
                    margin-bottom: 1.5rem;
                    border-bottom: 1px solid var(--dark-gray);
                }

                a {
                    font-size: 1.4rem;
                    font-weight: 700;
                    text-decoration: none;
                    color: var(--white);
                    transition: color .2s ease-in;

                    &:hover {
                        color: var(--primary-orange);
                    }
                }
                p {
                    margin-top: .5rem;
                    line-height: 170%;
                    color: var(--gray);
                }
            }
        }
    }

    @media screen and (max-width: 576px) {
        aside {
            padding: 1rem 1.2rem;
        }
    
        h1 {
            font-size: 2rem;
        }

        li {
            &:not(:last-child) {
                margin-bottom: 1rem;
            }
        }
    }
</style>