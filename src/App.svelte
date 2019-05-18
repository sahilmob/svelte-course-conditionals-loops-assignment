<script>
  let password = "";
</script>

<h1>Assignment</h1>

<input type="password" bind:value={password} />

{#if password.length < 5}
  <p>Too Short</p>
{:else if password.length > 10}
  <p>Too Long</p>
{:else}
  <p>{password}</p>
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
