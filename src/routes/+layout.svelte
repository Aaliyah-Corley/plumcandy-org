<script>
  import '../app.css';
  import { page } from '$app/stores';
</script>

<div class="min-h-screen flex flex-col font-sans text-slate-100 bg-slate-900 selection:bg-gold selection:text-slate-900">
  <header class="sticky top-0 z-50 w-full backdrop-blur-md bg-slate-900/80 border-b border-slate-800/50">
    <div class="container mx-auto px-4 h-16 flex items-center justify-between">
      <a href="/" class="text-xl font-serif font-bold text-gold tracking-tight hover:text-white transition-colors">
        Plum Candy Foundation
      </a>
      
      <nav class="hidden md:flex items-center gap-8 text-sm font-medium">
        <a href="/" class="hover:text-gold transition-colors {$page.url.pathname === '/' ? 'text-gold' : 'text-slate-400'}">Home</a>
        <a href="/tokenomics" class="hover:text-gold transition-colors {$page.url.pathname === '/tokenomics' ? 'text-gold' : 'text-slate-400'}">Tokenomics</a>
        <a href="/ea-math" class="hover:text-gold transition-colors {$page.url.pathname === '/ea-math' ? 'text-gold' : 'text-slate-400'}">EA Math</a>
      </nav>
    </div>
  </header>

  <main class="flex-1">
    <slot />
  </main>

  <footer class="py-12 border-t border-slate-800/50 text-center text-slate-500 text-sm">
    <p>&copy; {new Date().getFullYear()} Plum Candy Foundation. 501(c)(3).</p>
  </footer>
</div>
