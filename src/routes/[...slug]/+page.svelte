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
    // Removed canon logic as the search box section is removed.
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
            class="text-xl md:text-2xl text-slate-400 max-w-3xl mx-auto font-light leading-relaxed"
        >
            A non-profit whose mission is to make high school kids less dumb.
        </p>
    </section>

    <!-- Canon Lookup (Interactive) - REMOVED -->

    <!-- Content Sections -->
    <section class="grid md:grid-cols-2 gap-12 items-center">
        <div class="space-y-6">
            <h2 class="text-3xl font-serif text-slate-100">A Worthy Hero</h2>
            <p class="text-lg text-slate-300 leading-relaxed">
                We make high school kids less dumb by giving them a worthy hero
                — and making her novel, <a
                    href="https://aaliyah.com.br/plum-candy"
                    target="_blank"
                    rel="noopener noreferrer"
                    class="text-gold italic hover:underline">Plum Candy</a
                >,
                <a
                    href="https://itscanon.com/plum-candy"
                    target="_blank"
                    rel="noopener noreferrer"
                    class="text-gold hover:underline"
                    >culturally ubiquitous and fervently discussed in classrooms</a
                >.
            </p>
            <div class="mt-8 space-y-4">
                <h3 class="text-xl font-bold text-slate-100">
                    The Achiever Archetype
                </h3>
                <p class="text-lg text-slate-300 leading-relaxed">
                    Plum Candy is not just a great noir mystery. It’s the meta
                    story of the author, Aaliyah. The fact that a real
                    17-year-old wrote this is the Pedagogical Holy Grail.
                    Teachers can point to her and say: "She worked hard. She did
                    it. Maybe you can too!"
                </p>
            </div>
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

    <section class="space-y-8 text-left max-w-3xl mx-auto">
        <h2 class="text-3xl font-serif text-slate-100">Cultural Gold</h2>
        <p class="text-lg text-slate-300 leading-relaxed">
            Our roadmap to cultural influence will be financed through generous
            donations, yes, but principally through a sophisticated new digital
            asset: <a
                href="/tokenomics"
                class="text-gold font-serif italic hover:underline"
                >cultural gold</a
            >.
        </p>

        <div class="space-y-8 mt-8">
            <div class="space-y-4">
                <h3 class="text-xl font-bold text-slate-100">
                    The Capital Engine
                </h3>
                <p class="text-lg text-slate-300 leading-relaxed">
                    Financial patrons get 'Rookie Card' bundles. They are paying
                    for the status of being “first,” with a convex payoff
                    function.
                </p>
                <p class="text-lg text-slate-300 leading-relaxed">
                    First edition “value” has traditionally been lost to any
                    rando who happened to be in a 1998 bookstore with £2 to buy
                    an unknown Harry Potter, that’s now worth $500k.
                </p>
                <p class="text-lg text-slate-300 leading-relaxed">
                    You’re capturing value that was always there, but forfeited.
                    We're using that value to compound upon itself while helping
                    make high school kids less dumb.
                </p>
            </div>

            <div class="space-y-2">
                <h3 class="text-xl font-bold text-slate-100">
                    Concave (Standard Charity)
                </h3>
                <p class="text-lg text-slate-300 leading-relaxed">
                    You give $500k. They do charity stuff. You helped some kids.
                    The $500k is gone. You have to work to make another $500k to
                    give again. It is a "single-turn game."
                </p>
            </div>

            <div class="space-y-2">
                <h3 class="text-xl font-bold text-slate-100">
                    Convex (Cultural Gold)
                </h3>
                <p class="text-lg text-slate-300 leading-relaxed">
                    You buy $500k of PLUM. We do charity stuff. If the novel
                    misses, you still helped kids. But if the novel is a hit?
                    You get an outsized payoff. You can now fund <em
                        class="italic">more</em
                    > literacy.
                </p>
            </div>

            <div class="space-y-4">
                <h3 class="text-xl font-bold text-slate-100">Impact engine</h3>
                <p class="text-lg text-slate-300 leading-relaxed">
                    All the money raised funds the mission.
                </p>
                <p class="text-lg text-slate-300 leading-relaxed">
                    We mail a teacher’s edition of Plum Candy to 100,000 High
                    School English Professors.<br />
                    Offer them a 3-year grant, for their whole school, if they can
                    prove they read the book.<br />
                    Carpet-bomb basic copies out to celebs, CEOs, and college students.<br
                    />
                    Create a manhwa. Make the movie.
                </p>
            </div>

            <div class="pt-4">
                <p class="text-2xl font-serif text-gold italic">
                    Zero to One for Culture.
                </p>
            </div>
        </div>
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
