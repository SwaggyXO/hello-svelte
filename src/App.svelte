<script>
  const name = "YourMom"
  const test = "<b> HEHEHA </b>"
  const id = "hehe"
  const disabled = false
  const status = 'success';
  const promoted = true;
  const num = 0;
  const movies = ['Oppenheimer', 'Batman Begins', 'Avengers: End Game', 'Interstellar']
  const movieInfo = [
    {id: 1, movieName: 'Oppenheimer', director: 'Christopher Nolan'},
    {id: 2, movieName: 'Batman Begins', director: 'Christopher Nolan'},
    {id: 3, movieName: 'The Dark Knight', director: 'Christopher Nolan'},
    {id: 4, movieName: 'Interstellar', director: 'Christopher Nolan'},
  ]
  let count = 0;

  const increment = (e, num) => count += num;

  const reset = (e) => count = 0;

  const formValues = 
  {
    name: '',
    profileSummary: '',
    country: '',
    jobLocation: [],
    remoteWork: false,
    skillSet: [],
    experience: '',
  }

  const handleSubmit = () => {
    console.log(formValues);
  }
</script>

<main>
  <!-- <h1> {name} </h1>
  <h1> {@html test} </h1>
  <h1 {id} > Testing shorthand {id} </h1>
  <button {disabled} > Binding </button>
  <h2 class={status} > Text Test </h2>
  <h2 class:promoted > Movie </h2> Special directiv provided by svelte class:cssClass={varName} if var name and css class different -->
  <!-- {#if num > 0}
    <h2> Num is {num} </h2>
    {:else}
    <h2> Num is 0 </h2>
  {/if}

  {#each movies as movie, index}
    <h2> {index} {movie} </h2>
  {/each}

  {#each movieInfo as movie, idx (movie.id)}
    <h2> {movie.movieName} </h2>
    <h4> Directed by {movie.director} </h4> 
  {/each}

  <button on:click={(e) => increment(e, 5)}> Current count {count} </button>
  <button on:click={reset}> Reset </button> -->

  <div>
    <pre> {JSON.stringify(formValues, null, 1)} </pre>
  </div>

  <form on:submit|preventDefault={handleSubmit}> <!-- Event modifiers - svelete special -->
    <div>
      <label for="Name">Name</label>
      <input type="text" name="Name" id="name" bind:value={formValues.name} />
    </div>

    <div>
      <label for="profile">Profile Summary</label>
      <textarea id="profile" cols="30" rows="10" bind:value={formValues.profileSummary} />
    </div>

    <div>
      <label for="country">Country</label>
      <select id="country" bind:value={formValues.country}>
        <option value=""> Select a country </option>
        <option value="india">India</option>
        <option value="australia">Australia</option>
        <option value="iceland">Iceland</option>
      </select>
    </div>

    <div>
      <label for="jobloc">Job Location (select any 2)</label>
      <select id="jobloc" bind:value={formValues.jobLocation} multiple>
        <option value=""> Select a country </option>
        <option value="india">India</option>
        <option value="australia">Australia</option>
        <option value="newzealand">New Zealand</option>
        <option value="iceland">Iceland</option>
      </select>
    </div>

    <div>
      <label for="remoteWork">Open to work remotely?</label>
      <input type="checkbox" id="remoteWork" bind:checked={formValues.remoteWork}>
    </div>

    <div>
      <label for="skillSet">Skills</label> <br>
      <label for="frontend">Frontend Development</label>
      <input type="checkbox" id="fd" value="frontend" bind:group={formValues.skillSet}/>
      <label for="backend">Backend Development</label>
      <input type="checkbox" id="bd" value="backend" bind:group={formValues.skillSet}/>
      <label for="ml">Machine Learning</label>
      <input type="checkbox" id="ml" value="ml" bind:group={formValues.skillSet}/>
      <label for="cloud">Cloud Services</label>
      <input type="checkbox" id="cs" value="cloud" bind:group={formValues.skillSet}/>
    </div>

    <div>
      <label for="experience">Years of Experience</label>
      <input type="radio" id="0-2" value="0-2" bind:group={formValues.experience}/>
      <label for="0-2">0 - 2</label>
      <input type="radio" id="2-4" value="2-4" bind:group={formValues.experience}/>
      <label for="2-4">2 - 4</label>
      <input type="radio" id="4-8" value="4-8" bind:group={formValues.experience}/>
      <label for="4-8">4 - 8</label>
      <input type="radio" id="10+" value="10+" bind:group={formValues.experience}/>
      <label for="10+">10+</label>
    </div>

    <div>
      <button> Submit </button>
    </div>
  </form>
</main>

<style>
  .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
    transition: filter 300ms;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
  .read-the-docs {
    color: #888;
  }

  .danger {
    color: red;
  }

  .success {
    color: green;
  }

  .promoted {
    font-style: italic;
  }
</style>
