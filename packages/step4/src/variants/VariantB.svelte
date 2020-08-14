<script>
  import App from '../components/App';
  
  const handleButtonClick = () => alert('The button has been clicked!');
</script>
  
<p>I simply removed the button ↓</p>
<App
  onButtonClick={handleButtonClick} />
  