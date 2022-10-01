<script>
    let title = ""
    let date = ""
</script>

<main>
    <h3>Basic information</h3>

    <label for="title">Title</label>
    <input name="title" type="text" bind:value={title}>

    <label for="time">Date of Report</label>
    <input name="time" type="date" bind:value={date}>
</main>