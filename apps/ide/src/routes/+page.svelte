<script lang="ts">
  import { invoke } from "@tauri-apps/api"
  let name = "";
  let result = "";

  const handleSubmit = async () => {
    result = await invoke("greet", { name });
  }
</script>

<h1>Welcome to SvelteKit</h1>
<form on:submit={handleSubmit}>
  <input bind:value={name} name="name" />
  <button type="submit">Submit</button>
</form>
<span>{result}</span>
