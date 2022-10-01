<script>
    
  let skills = []
  let skillToAdd = ""

  function addSkill(event){
    event.preventDefault()

      if(skills.find(s=> skillToAdd===s)){
        alert("Skill already exists")
        return
      }

      skills = [...skills, skillToAdd]
      skillToAdd = ""
    }
  

  function removeSkill(skill){
    skills = skills.filter(s => s!==skill)
  }


</script>

<main>

    <h3>Skill Section</h3>

    <ul>
        {#each skills as skill}
          <li>{skill}  <button on:click={()=>removeSkill(skill)}>Remove</button></li>
        {/each}
          <li>
            <form  on:submit={addSkill} >
              <input type="text" bind:value={skillToAdd} required/>
              <button>Add</button>
            </form>
          </li>
    </ul>

</main>