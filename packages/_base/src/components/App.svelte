<script>
  import AppContainer from './AppContainer';
  import Button from './Button';

  import './App.scss';

  const handleButtonClick = () => {
    alert('The button has been clicked!');
  };

</script>

<div class="app">
  <AppContainer>
    <Button onClick={handleButtonClick} />
  </AppContainer>
</div>
