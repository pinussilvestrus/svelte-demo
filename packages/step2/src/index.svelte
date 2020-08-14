<script>
  import App from './components/App';

  import dom from 'domtastic';

  import BlueButton from './components/BlueButton';

  const handleButtonClick = () => {
    const containerElement = dom('.app-container');

    containerElement
      .css('background', '#000')
      .append('<img src="/step2/resources/cat.jpg" width="50%" />');
  };
</script>
  
<App 
  buttonComponent={BlueButton}
  onButtonClick={handleButtonClick} />