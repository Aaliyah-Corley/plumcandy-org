<script>
    import { page } from "$app/stores";
    import { browser } from "$app/environment";

    let query = "";
    let result = "";

    // Auto-run when someone shares a link like /plum-candy
    $: if (browser && $page.url.pathname !== "/" && $page.url.pathname !== "") {
        query = decodeURIComponent($page.url.pathname.slice(1));
        runCanon();
    }

    function runCanon() {
        if (!query.trim()) {
            result = "";
            if (browser) {
                history.replaceState({}, "", "/");
            }
            return;
        }

        // ←←← YOUR CANON LOGIC GOES HERE ONLY ←←←
        result = query.toUpperCase() + " CANON"; // placeholder
        // ←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←

        if (browser) {
            history.replaceState({}, "", `/${encodeURIComponent(query)}`);
        }
    }
</script>

<div class="max-w-4xl mx-auto px-4 py-12 md:py-20 space-y-24">
    <!-- Hero Section -->
    <section class="text-center space-y-8">
        <h1
            class="text-5xl md:text-7xl font-serif font-bold text-slate-100 leading-tight"
        >
            The Plum Candy <span class="text-gold">Foundation</span>
        </h1>
        <p
            class="text-xl md:text-2xl text-slate-400 max-w-2xl mx-auto font-light leading-relaxed"
        >
            A non-profit whose mission is to make high school kids less dumb.
        </p>
    </section>

    <!-- Canon Lookup (Interactive) -->
    <section class="max-w-xl mx-auto">
        <div class="relative group">
            <div
                class="absolute -inset-1 bg-gradient-to-r from-gold to-amber-600 rounded-lg blur opacity-25 group-hover:opacity-50 transition duration-1000 group-hover:duration-200"
            ></div>
            <div class="relative">
                <input
                    type="text"
                    bind:value={query}
                    on:input={runCanon}
                    placeholder="Type something to check canon status..."
                    class="w-full bg-slate-900 border border-slate-700 text-slate-100 px-6 py-4 rounded-lg focus:outline-none focus:border-gold focus:ring-1 focus:ring-gold transition-all placeholder-slate-600 text-lg font-mono"
                />
            </div>
        </div>

        {#if result}
            <div
                class="mt-8 p-6 border border-gold/20 bg-gold/5 rounded-lg text-center animate-in fade-in slide-in-from-bottom-4 duration-500"
            >
                <p
                    class="text-gold font-mono text-xl md:text-2xl tracking-widest font-bold"
                >
                    {result}
                </p>
            </div>
        {/if}
    </section>

    <!-- Content Sections -->
    <section class="grid md:grid-cols-2 gap-12 items-center">
        <div class="space-y-6">
            <h2 class="text-3xl font-serif text-slate-100">A Worthy Hero</h2>
            <p class="text-slate-400 leading-relaxed">
                We do that by giving them a worthy hero—and making her novel, <span
                    class="text-slate-200 font-medium">Plum Candy</span
                >, culturally ubiquitous and fervently discussed in classrooms.
            </p>
            <a
                href="https://itscanon.com"
                class="inline-flex items-center text-gold hover:text-amber-400 transition-colors font-medium group"
            >
                Visit itscanon.com
                <svg
                    class="w-4 h-4 ml-2 transform group-hover:translate-x-1 transition-transform"
                    fill="none"
                    stroke="currentColor"
                    viewBox="0 0 24 24"
                    ><path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M17 8l4 4m0 0l-4 4m4-4H3"
                    ></path></svg
                >
            </a>
        </div>
        <div
            class="relative aspect-[4/5] md:aspect-square bg-slate-800 rounded-lg overflow-hidden border border-slate-700 shadow-2xl"
        >
            <img
                src="/less-dumb-pin.webp"
                alt="Plum Candy Novel Art"
                class="absolute inset-0 w-full h-full object-cover"
            />
        </div>
    </section>

    <section class="space-y-8 text-center max-w-3xl mx-auto">
        <h2 class="text-3xl font-serif text-slate-100">Cultural Gold</h2>
        <p class="text-slate-400 leading-relaxed text-lg">
            Our <a
                href="/roadmap"
                class="text-gold hover:underline decoration-gold/50 underline-offset-4"
                >roadmap to cultural influence</a
            >
            will be financed through generous donations, yes, but principally through
            a sophisticated new digital asset:
            <span class="text-gold font-serif italic">cultural gold</span>.
        </p>
    </section>

    <!-- Quote -->
    <section class="py-12 border-y border-slate-800/50">
        <blockquote class="text-center space-y-6">
            <p
                class="text-2xl md:text-3xl font-serif italic text-slate-300 leading-relaxed"
            >
                “It’s been my goal for a while. A lot of people were like, ‘Come
                on… You can’t do that.’ But if you work on it for a long time,
                you can actually do it.”
            </p>
            <footer class="text-gold font-medium tracking-wide">
                — Aaliyah Corley
            </footer>
        </blockquote>
    </section>

    <section class="grid md:grid-cols-2 gap-12">
        <div class="space-y-6">
            <h3 class="text-2xl font-serif text-slate-100">The Vision</h3>
            <p class="text-slate-400 leading-relaxed">
                The world is complex and beautiful, and we’re all being
                shortchanged by shallow culture. Let’s fix that.
            </p>
        </div>
        <div class="space-y-6">
            <h3 class="text-2xl font-serif text-slate-100">The Model</h3>
            <p class="text-slate-400 leading-relaxed">
                If the model itself is successful, then it could become a model
                that other artists use to create a cultural asset.
            </p>
        </div>
    </section>

    <section
        class="bg-slate-800/50 rounded-2xl p-8 md:p-12 border border-slate-700 text-center space-y-6"
    >
        <h2 class="text-3xl font-serif text-gold">Zero to One for Culture</h2>
        <p class="text-slate-300 leading-relaxed max-w-2xl mx-auto">
            That further enhances the rookie status. It’s not just the rookie
            card of Plum candy. It’s a rookie card of how cultural gold was
            first created.
        </p>
    </section>
</div>
