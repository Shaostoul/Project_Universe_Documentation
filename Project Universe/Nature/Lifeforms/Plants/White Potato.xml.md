<LifeForm>
	<SingularName>white potato</SingularName>
	<PluralName>white potatoes</PluralName>
	<Type>plant</Type>
	<BodySamples>
		<Sample>*/lifeforms/plant/white_potato.blend</Sample>
	</BodySamples>
	<BodyParts>
		<Part name="shoot">
			<Part name="stem"/>
			<Part name="leaves"/>
			<Part name="flowers">
				<Part name="petal"/>
				<Part name="pistil"/>
				<Part name="stamen"/>
			</Part>
		</Part>
		<Part name="root">
			<Part name="main_root"/>
			<Part name="tubers"><!-- The part we commonly eat -->
				<Part name="skin"/>
				<Part name="flesh"/>
				<Part name="eyes"/>
			</Part>
		</Part>
	</BodyParts>
	<Size>
		<Height centimeters="61"/>
		<Weight grams="680"/>
	    <AboveGround>
	        <PlantingRadius centimeters="35±5"/>
	        <CanopyRadius centimeters="50±10"/>
	    </AboveGround>
	    <BelowGround>
	        <RootDepth centimeters="30±5"/>
	        <RootRadius centimeters="40±8"/>
	    </BelowGround>
	</Size>
	<NutritionRequired>
		<Water>
			<Frequency hours="60±12"/> <!-- Hours between waterings -->
			<Drainage percent="70"/><!-- 0 (no drainage) 100 (max drainage) -->
			<DryBeforeWatering value="true"/>
		</Water>
		<Sunlight hours="7±1" lux="5000"/><!-- daily -->
		<Acidity pH="6±1"/>
		<Temperature>
			<VegetativeGrowth Fahrenheit="60±5"/>
			<ReproductiveGrowth Fahrenheit="60±5"/>
		</Temperature>
		<Nutrient name="N" grams="5"/><!-- Nitrogen -->
		<Nutrient name="P" grams="4"/><!-- Phosphorus -->
		<Nutrient name="K" grams="10"/><!-- Potassium -->
		<Nutrient name="Ca" grams="3"/><!-- Calcium -->
		<Nutrient name="Mg" grams="2"/><!-- Magnesium -->
		<Nutrient name="S" grams="1"/><!-- Sulfur -->
		<Nutrient name="Fe" grams="0.02"/><!-- Iron -->
		<Nutrient name="Mn" grams="0.015"/><!-- Manganese -->
		<Nutrient name="Zn" grams="0.01"/><!-- Zinc -->
		<Nutrient name="Cu" grams="0.005"/><!-- Copper -->
		<Nutrient name="B" grams="0.002"/><!-- Boron -->
		<Nutrient name="Mo" grams="0.001"/>  <!-- Molybdenum -->
		<Nutrient name="Cl" grams="0.02"/><!-- Chlorine -->
	</NutritionRequired>
	<NutritionProduced>
		<!-- per 150 grams -->
		<Water percent="78"/><!-- 0 (no water) to 100 (all water) -->
		<Nutrient name="Calories" kilocalories="164"/>
	    <Nutrient name="Protein" grams="4.4"/>
	    <Nutrient name="Carbohydrates" grams="37"/>
	    <Nutrient name="TotalFat" grams="0.22"/>
	    <Nutrient name="Fiber" grams="3.8"/>
		<Nutrient name="C" grams="0.02"/>
		<Nutrient name="B6" grams="0.0005"/>
		<Nutrient name="K" grams="0.9"/>
		<Nutrient name="Mg" grams="0.048"/>
		<Nutrient name="Fe" grams="0.0018"/>
	</NutritionProduced>
	<SeedStorage>
	    <Temperature Fahrenheit="35±2"/>
	    <Humidity percent="15±5"/>
	    <Light lux="0"/>
	    <Duration years="5±2"/>
	</SeedStorage>
	<DaysUntil>
	    <Sprouting days="7±2"/>
	    <Germination days="21±5"/>
	    <Maturity days="70±15"/>
	    <Harvest days="120±20"/>
	    <Death days="150"/>
	</DaysUntil>
	<Growth rate="5±2"/><!-- grams/day -->
	<EnvironmentalNeeds>
		<Water>
			<Frequency hours="60±12"/> <!-- Hours between waterings -->
			<Drainage percent="70"/><!-- 0 (no drainage) 100 (max drainage) -->
			<DryBeforeWatering value="true"/>
		</Water>
		<Sunlight hours="7±1" lux="5000"/><!-- daily -->
		<Acidity pH="6±1"/>
		<Temperature>
			<VegetativeGrowth Fahrenheit="60±5"/>
			<ReproductiveGrowth Fahrenheit="60±5"/>
		</Temperature>
	</EnvironmentalNeeds>
</LifeForm>