# code-clause-task-1

<!DOCTYPE html>
<html>
<head>
	<title>Unit Converter</title>
    <link rel="icon" type="image/x-icon" href="bg.png">
    <style>
    body
        {
            
			/* background-image:url("preview.png"); */
			background-color: darkolivegreen;
			 
	    }
    form
    {
        position: absolute;
        top: 50%; left: 50%;
        transform: translate(-50%, -50%);
    }
    .converter-box
    {
        border: 2px solid black;
        border-radius: 5px;
        padding: 20px;
        display:inline-block;
        margin-top: 200px;
    }
    </style>
</head>
<body><center>
    <div class="converter-box">
	<h1>Unit Converter</h1>
    <label for="output"><strong>Input</strong></label>
    <input type="number" id="input">
	
	<!-- Length units -->
	<label for="output"><strong>from</strong></label>
	<select id="from">
		<option value="cm">cm</option>
		<option value="m">m</option>
		<option value="km">km</option>
	</select>
	<label for="output"><strong>to</strong></label>
	<select id="to">
		<option value="cm">cm</option>
		<option value="m">m</option>
		<option value="km">km</option>
	</select>
	
	<!-- Temperature units -->
	<label for="output"><strong>from</strong></label>
	<select id="temp-from">
		<option value="C">Celsius</option>
		<option value="F">Fahrenheit</option>
		<option value="K">Kelvin</option>
	</select>
	<label for="output"><strong>to</strong></label>
	<select id="temp-to">
		<option value="C">Celsius</option>
		<option value="F">Fahrenheit</option>
		<option value="K">Kelvin</option>
	</select>
	
	<button onclick="convert()">Convert</button>
    <br>
    
	<!-- Length units -->
	<label for="output"><strong>Result (length):</strong></label>
	<input type="text" id="output" readonly>
	
	<!-- Temperature units -->
	<label for="temp-output"><strong>Result (temperature):</strong></label>
	<input type="text" id="temp-output" readonly>
    
	<script>
		function convert() {
			// Get length input value and units
			let lengthValue = parseFloat(document.getElementById("input").value);
			let fromUnit = document.getElementById("from").value;
			let toUnit = document.getElementById("to").value;

			// Convert length units
			if (fromUnit === "cm" && toUnit === "m") {
				lengthValue /= 100;
			} else if (fromUnit === "cm" && toUnit === "km") {
				lengthValue /= 100000;
			} else if (fromUnit === "m" && toUnit === "cm") {
				lengthValue *= 100;
			} else if (fromUnit === "m" && toUnit === "km") {
				lengthValue /= 1000;
			} else if (fromUnit === "km" && toUnit === "cm") {
				lengthValue *= 100000;
			} else if (fromUnit == "km" && toUnit === "m") 
            inputValue *= 1000;
			} else {
				// Units are the same, no conversion needed
				inputValue = parseFloat(document.getElementById("input").value);
			}

			// Display result
			document.getElementById("output").value = inputValue.toFixed(2);
		
	</script>
    </div>
    </center>
</body>
</html>
