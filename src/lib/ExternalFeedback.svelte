<script>
    let title = "";
    let link = "";
    let feedBackInfo = ""


    let clientFeedbacks = []

    function addFeedbackLink(e){
        e.preventDefault()
        clientFeedbacks= [...clientFeedbacks,{title,link}]
    }

    function removeLink(title){
        clientFeedbacks = clientFeedbacks.filter(c => c.title!==title)
    }


</script>

<main>

    <h3>External Feedback</h3>

    <textarea cols="30" rows="10" bind:value={feedBackInfo} placeholder="Next Steps to improve competency"></textarea>

    <h5>Feedback Links</h5>
    <ul>
        {#each clientFeedbacks as c}
            <li><a href={c.link}>{c.title}</a> <button on:click={()=>removeLink(c.title)}>Remove</button></li>
        {/each}
    </ul>

    <h5>Interview Links</h5>
    <form on:submit={addFeedbackLink}>
        <input type="text" bind:value={title} required>
        <input type="text" bind:value={link} required>
        <button>Add</button>
    </form>
</main>