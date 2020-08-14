<script>
  import AppContainer from './AppContainer';

  import './App.scss';

  const noop = () => {};

  const handleClick = () => {
    onButtonClick();
  };

  export let buttonComponent;
  export let onButtonClick = noop;

</script>

<div class="app">
  <AppContainer>
    <svelte:component
      this={buttonComponent}
      onClick={handleClick} />
  </AppContainer>
</div>
