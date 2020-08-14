<script>
  import AppContainer from './components/AppContainer';
  import Button from './components/Button';

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
