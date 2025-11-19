<script>
  import "../app.css";
  import { page } from "$app/stores";

  let isMenuOpen = false;

  function toggleMenu() {
    isMenuOpen = !isMenuOpen;
  }

  function closeMenu() {
    isMenuOpen = false;
  }
</script>

<div
  class="min-h-screen flex flex-col font-sans text-slate-100 bg-slate-900 selection:bg-gold selection:text-slate-900"
>
  <header
    class="sticky top-0 z-50 w-full backdrop-blur-md bg-slate-900/80 border-b border-slate-800/50"
  >
    <div class="container mx-auto px-4 h-16 flex items-center justify-between">
      <a
        href="/"
        class="text-xl font-serif font-bold text-gold tracking-tight hover:text-white transition-colors"
        on:click={closeMenu}
      >
        Plum Candy Foundation
      </a>

      <!-- Desktop Nav -->
      <nav class="hidden md:flex items-center gap-8 text-sm font-medium">
        <a
          href="/"
          class="hover:text-gold transition-colors {$page.url.pathname === '/'
            ? 'text-gold'
            : 'text-slate-400'}">Home</a
        >
        <a
          href="/tokenomics"
          class="hover:text-gold transition-colors {$page.url.pathname ===
          '/tokenomics'
            ? 'text-gold'
            : 'text-slate-400'}">Tokenomics</a
        >
        <a
          href="/ea-math"
          class="hover:text-gold transition-colors {$page.url.pathname ===
          '/ea-math'
            ? 'text-gold'
            : 'text-slate-400'}">EA Math</a
        >
      </nav>

      <!-- Mobile Menu Button -->
      <button
        class="md:hidden text-slate-400 hover:text-gold focus:outline-none"
        on:click={toggleMenu}
        aria-label="Toggle menu"
      >
        <svg
          class="w-6 h-6"
          fill="none"
          stroke="currentColor"
          viewBox="0 0 24 24"
        >
          {#if isMenuOpen}
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M6 18L18 6M6 6l12 12"
            />
          {:else}
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16M4 18h16"
            />
          {/if}
        </svg>
      </button>
    </div>

    <!-- Mobile Nav Overlay -->
    {#if isMenuOpen}
      <div
        class="md:hidden absolute top-16 left-0 w-full bg-slate-900 border-b border-slate-800/50 shadow-xl"
      >
        <nav class="flex flex-col p-4 space-y-4 text-center">
          <a
            href="/"
            class="block py-2 hover:text-gold transition-colors {$page.url
              .pathname === '/'
              ? 'text-gold'
              : 'text-slate-400'}"
            on:click={closeMenu}>Home</a
          >
          <a
            href="/tokenomics"
            class="block py-2 hover:text-gold transition-colors {$page.url
              .pathname === '/tokenomics'
              ? 'text-gold'
              : 'text-slate-400'}"
            on:click={closeMenu}>Tokenomics</a
          >
          <a
            href="/ea-math"
            class="block py-2 hover:text-gold transition-colors {$page.url
              .pathname === '/ea-math'
              ? 'text-gold'
              : 'text-slate-400'}"
            on:click={closeMenu}>EA Math</a
          >
        </nav>
      </div>
    {/if}
  </header>

  <main class="flex-1">
    <slot />
  </main>

  <footer
    class="py-12 border-t border-slate-800/50 text-center text-slate-500 text-sm"
  >
    <p>&copy; {new Date().getFullYear()} Plum Candy Foundation. 501(c)(3).</p>
  </footer>
</div>
