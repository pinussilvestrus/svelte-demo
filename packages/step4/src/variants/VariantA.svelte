<script>
  import App from '../components/App';
  import Button from '../components/Button';

  const handleButtonClick = () => alert('The button has been clicked!');
</script>

<App
  buttonComponent={Button}
  onButtonClick={handleButtonClick} />
