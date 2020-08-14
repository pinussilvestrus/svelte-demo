<script>
  import App from '../components/App';
  import BlueButton from '../components/BlueButton';
  
  const handleButtonClick = () => alert('The button has been clicked!');
</script>
  
<App
  buttonComponent={BlueButton}
  onButtonClick={handleButtonClick} />
  