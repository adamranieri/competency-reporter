<script>

    let feedback=[{batch:"example Batch",date:"9/13", curriculum:"JWA 2.1", associateCount:19, compQcScore:4.1, overallQcScore:3.6, cap:17, id:1}]

    let batch = ""
    let date = ""
    let curriculum = ""
    let associateCount = 0
    let compQcScore = 0
    let overallQcScore =0
    let cap = 0

    function addFeedback(event){
        event.preventDefault()
        feedback =[...feedback, {batch,date,curriculum,associateCount,compQcScore,overallQcScore,cap, id: Math.random()}]
    }

    function removeFeedBack(id){
        feedback = feedback.filter(f => f.id!==id)
    }

</script>

<main>

    <h3>Internal Feedback</h3>

    <table>
        <thead>
            <tr>
                <th>Batch</th>
                <th>Date</th>
                <th>Curriculum</th>
                <th>Associate Count</th>
                <th>Competency QC Score</th>
                <th>Overall QC Score</th>
                <th>Competency Assessment Score</th>
            </tr>
        </thead>
        <tbody>
            {#each feedback as  f}
            <tr>
                <td>{f.batch}</td>
                <td>{f.date}</td>
                <td>{f.curriculum}</td>
                <td>{f.associateCount}</td>
                <td>{f.compQcScore}</td>
                <td>{f.overallQcScore}</td>
                <td>{f.cap}</td>
                <td><button on:click={()=>removeFeedBack(f.id)}>Remove</button></td>
            </tr>
            {/each}
        </tbody>
    </table>

    <form on:submit={addFeedback}>

        <fieldset>
            <legend>Batch Information</legend>

            <label for="batch">Batch</label>
            <input name="batch" type="text" bind:value={batch} required/>

            <label for="">Date</label>
            <input type="date" bind:value={date} required/>

            <label for="Curriculum">Curriculum</label>
            <input type="text" bind:value={curriculum} required/>

            <label for="count">Associate Count</label>
            <input type="number" bind:value={associateCount} required/>
        </fieldset>

        <fieldset>
            <legend>Evaluations</legend>

            <label for="">Competency QC Score</label>
            <input type="number" bind:value={compQcScore} required/>

            <label for="">Overall QC Score</label>
            <input type="number" bind:value={overallQcScore} required/>

            <label for="">Competency Assessment Score</label>
            <input type="number" bind:value={cap} required/>
        </fieldset>
        <button>Add</button>


    </form>

</main>