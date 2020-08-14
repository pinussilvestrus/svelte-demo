<script>
  import AppContainer from './AppContainer';

  import './App.scss';

  export let buttonComponent;
  export let onButtonClick;

</script>

<div class="app">
  <AppContainer>
    <svelte:component
      this={buttonComponent}
      onClick={onButtonClick} />
  </AppContainer>
</div>
