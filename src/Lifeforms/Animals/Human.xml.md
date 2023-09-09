<LifeForm>
	<SingularName language="English">human</SingularName>
	<PluralName language="English">humans</PluralName>
	<Type>animal</Type>
	<DefaultStats>
		<StandHeight centimeter>180</StandHeight>
		<CrouchHeight centimeter>60</CrouchHeight>
		<ProneHeight centimeter>30</ProneHeight>
		<Weight kilogram>70</Weight>
	    <SprintSpeed kmh="44.72"/>
	    <RunSpeed kmh="20.92"/>
	    <WalkSpeed kmh="14.5"/>
	    <CrouchSpeed kmh="7.25"/>
	    <ProneSpeed kmh="3.62"/>
	    <JumpHeight meters="2.45"/>
		<EncumbranceLight kg="15"/>
		<EncumbranceMedium kg="30"/>
		<EncumbranceHeavy kg="60"/>
		<CarryLong kg="150"/><!-- 100 meters -->
		<CarryShort kg="500"/><!-- 20 meters -->
	<DefaultStats>
	<BodySamples><!-- Volunteer submissions welcome! -->
		<Sample>*/lifeforms/human/volunteer_shaostoul.blend</Sample><!-- 3D model N/A -->
	</BodySamples>
	<BodyParts>
		<Part name="head">
			<Part name="crown"/>
			<Part name="forehead"/>
			<Part name="left_ear"/>
			<Part name="right_ear"/>
			<Part name="left_brow"/>
			<Part name="left_eye"/>
			<Part name="right_brow"/>
			<Part name="right_eye"/>
			<Part name="nose"/>
			<Part name="mouth"/>
			<Part name="chin"/>
		</Part>
		<Part name="neck"/>
		<Part name="collar"/>
		<Part name="left_arm">
			<Part name="shoulder"/>
			<Part name="upper_arm"/>
			<Part name="elbow"/>
			<Part name="forearm"/>
			<Part name="wrist"/>
			<Part name="hand">
				<Part name="palm"/>
				<Part name="thumb"/>
				<Part name="index_finger"/>
				<Part name="middle_finger"/>
				<Part name="ring_finger"/>
				<Part name="pinky_finnger"/>
			</Part>
		</Part>
		<Part name="right_arm">
			<Part name="shoulder"/>
			<Part name="upper_arm"/>
			<Part name="elbow"/>
			<Part name="forearm"/>
			<Part name="wrist"/>
			<Part name="hand">
				<Part name="palm"/>
				<Part name="thumb"/>
				<Part name="index_finger"/>
				<Part name="middle_finger"/>
				<Part name="ring_finger"/>
				<Part name="pinky_finnger"/>
			</Part>
		</Part>
		<Part name="chest">
			<Part name="left_breast">
				<Part name="nipple"/>
			</Part>
			<Part name="right_breast">
				<Part name="nipple"/>
			</Part>
		</Part>
		<Part name="waist">
			<Part name="belly_button"/>
		</Part>
		<Part name="left_hip">
			<Part name="left_thigh"/>
			<Part name="left_knee"/>
			<Part name="left_shin"/>
			<Part name="left_ankle"/>
			<Part name="left_foot">
				<Part name="left_heel"/>
				<Part name="left_sole"/>
				<Part name="left_big_toe"/>
				<Part name="left_index_toe"/>
				<Part name="left_middle_toe"/>
				<Part name="left_ring_toe"/>
				<Part name="left_pinky_toe"/>
			</Part>
		</Part>
		<Part name="right_hip">
			<Part name="right_thigh"/>
			<Part name="right_knee"/>
			<Part name="right_shin"/>
			<Part name="right_ankle"/>
			<Part name="right_foot">
				<Part name="right_heel"/>
				<Part name="right_sole"/>
				<Part name="right_big_toe"/>
				<Part name="right_index_toe"/>
				<Part name="right_middle_toe"/>
				<Part name="right_ring_toe"/>
				<Part name="right_pinky_toe"/>
			</Part>
		</Part>
		<Part name="groin"><!-- defaults to no genitals -->
			<Part sex="default" genitals="nothing"/>
			<Part sex="male" genitals="penis"/>
			<Part sex="female" genitals="vagina"/>
		</Part>
	</BodyParts>
	<NutritionNeeds><!-- daily -->
		<Water liters="3"/>
		<Kilocalories value="2500"/>
		<Nutrient name="Protein" grams="56"/>
		<Nutrient name="Carbohydrates" grams="310"/>
		<Nutrient name="TotalFat" grams="70"/>
		<Nutrient name="SaturatedFat" grams="24"/>
		<Nutrient name="Fiber" grams="38"/>
		<Nutrient name="A" grams="0.0009"/>
		<Nutrient name="C" grams="0.09"/>
		<Nutrient name="D" grams="0.00002"/>
		<Nutrient name="E" grams="0.015"/>
		<Nutrient name="K" grams="0.00012"/>
		<Nutrient name="B1" grams="0.0012"/>
		<Nutrient name="B2" grams="0.0013"/>
		<Nutrient name="B3" grams="0.016"/>
		<Nutrient name="B5" grams="0.005"/>
		<Nutrient name="B6" grams="0.0013"/>
		<Nutrient name="B7" grams="0.00003"/>
		<Nutrient name="B9" grams="0.0004"/>
		<Nutrient name="B12" grams="0.0000024"/>
		<Nutrient name="Choline" grams="0.00055"/>
		<Nutrient name="Ca" grams="1"/> <!-- Calcium -->
		<Nutrient name="Cl" grams="2.3"/> <!-- Chloride -->
		<Nutrient name="Mg" grams="0.42"/> <!-- Magnesium -->
		<Nutrient name="P" grams="0.7"/> <!-- Phosphorus -->
		<Nutrient name="K" grams="4.7"/> <!-- Potassium -->
		<Nutrient name="Na" grams="1.5"/> <!-- Sodium -->
		<Nutrient name="S" grams="0.8"/> <!-- Sulfur -->
		<Nutrient name="Cr" grams="0.000035"/> <!-- Chromium -->
		<Nutrient name="Cu" grams="0.0009"/> <!-- Copper -->
		<Nutrient name="I" grams="0.00015"/> <!-- Iodine -->
		<Nutrient name="Fe" grams="0.008"/> <!-- Iron -->
		<Nutrient name="Mn" grams="0.0023"/> <!-- Manganese -->
		<Nutrient name="Mo" grams="0.000045"/> <!-- Molybdenum -->
		<Nutrient name="Se" grams="0.000055"/> <!-- Selenium -->
		<Nutrient name="Zn" grams="0.011"/> <!-- Zinc -->
		<Nutrient name="F" grams="0.004"/> <!-- Fluoride -->
	</NutritionNeeds>
</LifeForm>