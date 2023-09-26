<script>
  import svelteLogo from './assets/svelte.svg'
  import CcForm from './lib/CCForm.svelte'
  import CcVisual from './lib/CCVisual.svelte';

  let name = '';
  let ccnumber;
  let expMonth;
  let expYear;
  let cvc;
</script>

<main>
  <CcVisual bind:name bind:ccnumber bind:expMonth bind:expYear bind:cvc />
</main>
<aside>
  <CcForm bind:name bind:ccnumber bind:expMonth bind:expYear bind:cvc />
</aside>

<style>
  main {
    background: url('./assets/bg-main-mobile.png') center center/cover no-repeat;
    height: 172px;
    padding: 36px 20px;
  }
</style>
