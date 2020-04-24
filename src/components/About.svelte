<script>
  let someText = `Frontend Developer at Platzi`;
  let count = 0;
  let styles = { darkMode: false }

  function handleClick () {
    count += 1;
  }

  function toggle () {
    styles.darkMode = !styles.darkMode;
    window.document.body.classList.toggle('dark-mode');
  }

</script>

<style>
  p {
		color: var(--theme-color);
		font-size: 22px;
  }
  
  .light-mode {
    color:var(--secondary);
  }

  .dark-mode {
    color: var(--primary);
  }

</style>

<div class={`About ${!styles.darkMode ? 'light-mode' : 'dark-mode'}`}>

  {#if !styles.darkMode}
    <p>{someText}</p>
  {:else}
    <p>Hello DarMode</p>
  {/if}
  <button on:click={handleClick}>Click {count === 0 ? '' : count} </button>
  <button on:click={toggle}>DarkMode</button>
</div>