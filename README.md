<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset = "utf-8">
        <meta name="generator" content="FET-IUH IoT Team">
        <meta name= "dcterms.created" content="T5, 24 Thg3 2022 08:00:00 GMT">
        <meta name= "description" content="Design Platform for IoT Laboratory">
        <meta name= "keywords" content="Internet of things, LoraWan, Raspberry Pi 4">
        <title>Sample Website of FET-IUH IoT Team</title>
    </head>
	<body>
		<h2 align = center>*- LED Control Website -*</h2>
		<div align = center>
			<p>
				<font color= "red"><b>FET-IUH IoT Laboratory</b></font><br />
				<font color= "blue">Design Platform for IoT Laboratory</font><br />
			</p>
			<p>
				<font color= "green">Click on button for control LED</font><br />
				<button onclick="LED_On()">ON</button> 
				<button onclick="LED_Off()">OFF</button>
			</p>
		</div>
		<div align = left>
			<p>
				<font color="red">-*- LED CONTROL -*-</font></br>
					<iframe width="450" height="260" style="border: 1px solid #cccccc;" src="https://thingspeak.com/channels/1683938/charts/3?bgcolor=%23ffffff&color=%23d62020&dynamic=true&results=60&type=line&update=15"></iframe>			
			</p>
		</div>
		<div align = left>
			<p>
				<font color="blue">-*- TEMPERATURE -*-</font></br>
					<iframe width="450" height="260" style="border: 1px solid #cccccc;" src="https://thingspeak.com/channels/1683938/charts/1?bgcolor=%23ffffff&color=%23d62020&dynamic=true&results=60&type=line&update=15"></iframe>
			</p>
		</div>
		<div align = left>
			<p>
				<font color="black">-*- HUMI -*-</font></br>
					<iframe width="450" height="260" style="border: 1px solid #cccccc;" src="https://thingspeak.com/channels/1683938/charts/2?bgcolor=%23ffffff&color=%23d62020&dynamic=true&results=60&type=line&update=15"></iframe>
			</p>
		</div>
		<script>
			var url = "https://api.thingspeak.com/update?";
			var params_on = "api_key=KEJ1UWDEVTJV1TNL&field3=1";
			var params_off = "api_key=KEJ1UWDEVTJV1TNL&field3=0";
			var xhr = new XMLHttpRequest();
			
			function LED_On()
			{
				xhr.open("POST",url,true);
				xhr.setRequestHeader("Content-type","application/x-www-form-urlencoded");
				xhr.send(params_on);
			}
			function LED_Off()
			{
				xhr.open("POST",url,true);
				xhr.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
				xhr.send(params_off);
			}
			
		</script>
	</body>
</html>
