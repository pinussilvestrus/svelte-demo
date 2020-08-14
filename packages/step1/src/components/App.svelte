<script>
  import AppContainer from './AppContainer';

  import './App.scss';

  const handleButtonClick = () => {
    alert('The button has been clicked!');
  };

  export let buttonComponent;

</script>

<div class="app">
  <AppContainer>
    <svelte:component
      this="{buttonComponent}"
      onClick={handleButtonClick} />
  </AppContainer>
</div>
