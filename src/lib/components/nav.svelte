<script>
  import ThemeSwitch from './theme-switch.svelte'
</script>

<nav class="navbar bg-base-100 py-4 pb-20">
  <div class="flex-1">
    <a class="btn btn-ghost normal-case text-xl" href="/">
      Devcer
    </a>
  </div>
  <div class="flex-none">
    <ul class="menu menu-horizontal p-0">
      <li><a href="/about">About</a></li>
    </ul>
    <ThemeSwitch />
  </div>
</nav>