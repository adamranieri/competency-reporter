<script>

    let title = "";
    let link = "";

    let curricula = []

    function addCurriculum(e){
        e.preventDefault()
        curricula= [...curricula,{title,link}]
    }

    function removeCurriculum(title){
        curricula = curricula.filter(c => c.title!==title)
    }


</script>

<main>

    <h3>Active Curricula</h3>

    <ul>
        {#each curricula as c}
            <li><a href={c.link}>{c.title}</a> <button on:click={()=>removeCurriculum()}>Remove</button></li>
        {/each}
    </ul>

    <form on:submit={addCurriculum}>
        <input type="text" bind:value={title} required>
        <input type="text" bind:value={link} required>
        <button>Add</button>
    </form>

</main>