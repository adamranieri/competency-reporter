
<script>
    import CurriculuaSection from "./lib/CurriculuaSection.svelte";
    import ExternalFeedback from "./lib/ExternalFeedback.svelte";
    import InternalFeedback from "./lib/InternalFeedback.svelte";
    import NextSteps from "./lib/NextSteps.svelte";
    import SkillSection from "./lib/SkillSection.svelte";
    import TitleSection from "./lib/TitleSection.svelte";


  /**@type {{
   * title: string, date: number, skills: string[], skillsRemoved: string[], skillsAdded: string[], 
   * curricula:{name:string, link:string}[], qualityGates:{name:string, link:string}[]
   * }} */
  let report = {title:"", date:0, skills:[], skillsAdded:[], skillsRemoved:[], curricula:[], qualityGates:[]}

  let title = ""
  let date = ""

</script>


<main>
  <h1>Competency Report Template</h1>

  <TitleSection/>

  <SkillSection/>

  <CurriculuaSection/>

  <InternalFeedback/>

  <ExternalFeedback/>

  <NextSteps/>

</main>
