<script lang="ts">
    const activities = Array.from({ length: 5 }, (_, i) => ({
    id: i + 1,
    img: '/cookies.jpg',
    main: {
        category: `Category`,
        title: `Title ${i}`,
        description: 'A nice description for this article that should be multiple lines.'
    },
    date: new Date().toISOString()
    }));
</script>

<main>
    <header>
        <h1 class="text-5xl">Libelle Vriendinnen</h1>
        <sub class="text-2xl"><i>Activiteiten</i></sub>
    </header>
    <section class="p-5 flex flex-wrap justify-around w-full">
        {#each activities as activity}
        <article class="flex flex-col max-w-[320px] mb-15">
                <div class="block shadow-2xl max-w-80 max-h-52 m-0 p-0">
                    <img class="h-full w-full object-cover overflow-clip" src={activity.img} alt={activity.main.title}>
                </div>
                <div id="main" class="block shadow-2xl mx-auto -mt-8 h-80 max-w-64 bg-pink-600 text-white p-5">
                    <span class="italic">{activity.main.category}</span>
                    <h2 class="text-4xl mt-1.5 mb-5">{activity.main.title}</h2>
                    <p class="text-xl">{activity.main.description}</p>
                </div>
        
            <div class="shadow-2xl size-24 bg-lime-500 ml-auto text-3xl flex items-center justify-center text-center -mt-4">
                <span>04</span>
                <span>JAN</span>
            </div>
            <a class="text-blue-600 hover:text-blue-800 transition-colors duration-100 underline" href="/activity/{activity.id}">Inschrijven</a>
        </article>
        {/each}
    </section>
</main>
