<script>
  let password = "";
  let passwords = [];

  function savePassword() {
    passwords = [...passwords, password];
    password = "";
  }

  function deletePassword(i) {
    passwords = passwords.filter((_, inedx) => inedx != i);
  }
</script>

<h1>Assignment</h1>

<input type="password" bind:value={password} />

{#if password.length < 5 && password.length > 0}
  <p>Too Short</p>
{:else if password.length > 10}
  <p>Too Long</p>
{:else}
  <p>{password}</p>
{/if}
<button
  disabled={password.length < 5 || password.length > 10}
  on:click={savePassword}>
  Save password
</button>

{#if passwords.length > 0}
  <p>Passwrds:</p>
  <ul>
    <!-- The assumption here is that every password is unique -->
    {#each passwords as password, i (password)}
      <li on:click={() => deletePassword(i)}>{password}</li>
    {/each}
  </ul>
{/if}

<p>Solve these tasks.</p>

<ol>
  <li>Add a password input field and save the user input in a variable.</li>
  <li>
    Output "Too short" if the password is shorter than 5 characters and "Too
    long" if it's longer than 10.
  </li>
  <li>
    Output the password in a paragraph tag if it's between these boundaries.
  </li>
  <li>Add a button and let the user add the passwords to an array.</li>
  <li>Output the array values (= passwords) in a unordered list (ul tag).</li>
  <li>Bonus: If a password is clicked, remove it from the list.</li>
</ol>
