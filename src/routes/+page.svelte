<script>
	// heading
	// headings: font options
	let headingFontOptions = ['Palatino', 'Futura', 'Courier New'];
	let selectedHeadingFont = headingFontOptions[0];

	// heading: color options
	let headingColorOptions = ['white', 'blue', 'black', 'gray'];
	let selectedHeadingColor = headingColorOptions[0];

	$: headingStyle = `color: ${selectedHeadingColor}; font-family: ${selectedHeadingFont}`;

	// paragraph
	// paragraph: font options
	let paragraphFontOptions = ['Palatino', 'Futura', 'Courier New'];
	let selectedParagraphFont = paragraphFontOptions[0];

	// paragraph: color options
	let paragraphColorOptions = ['white', 'blue', 'black', 'gray'];
	let selectedParagraphColor = paragraphColorOptions[0];

	$: paragraphStyle = `color: ${selectedParagraphColor}; font-family: ${selectedParagraphFont}`;

	// background
	let backgroundColorOptions = ['navy', 'white', 'lightgray', 'lightblue'];
	let selectedBackgroundColor = backgroundColorOptions[0];

	$: theme = `
h1, h2, h3, h4, h5, h6 {
  font-family: ${selectedHeadingFont};
  color: ${selectedHeadingColor};
}

body {
  font-family: ${selectedParagraphFont};
  color: ${selectedParagraphColor};
  background-color: ${selectedBackgroundColor};
}
		`;
</script>

<nav>
	<h1>Opinionated Plaintext Blog Themer</h1>
</nav>

<div class="row">
	<div class="column left" style="background-color: {selectedBackgroundColor}">
		<h1 style={headingStyle}>Example Heading 1</h1>
		<p style={paragraphStyle}>
			Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut
			labore et dolore magna aliqua. Tellus cras adipiscing enim eu turpis egestas pretium. At augue
			eget arcu dictum varius duis at. Pellentesque sit amet porttitor eget dolor morbi non. Urna et
			pharetra pharetra massa massa. Massa eget egestas purus viverra accumsan in nisl nisi
			scelerisque. Nam libero justo laoreet sit amet cursus sit amet. Morbi tincidunt ornare massa
			eget egestas purus viverra accumsan. Elementum nisi quis eleifend quam adipiscing vitae proin
			sagittis nisl. Ultrices vitae auctor eu augue ut lectus.
		</p>
		<h2 style={headingStyle}>Example Heading 2</h2>
		<p style={paragraphStyle}>
			Scelerisque varius morbi enim nunc faucibus. Morbi tristique senectus et netus et malesuada
			fames ac turpis. Eu tincidunt tortor aliquam nulla facilisi cras fermentum odio eu. Libero
			volutpat sed cras ornare arcu dui vivamus. Pretium vulputate sapien nec sagittis. Mi ipsum
			faucibus vitae aliquet nec ullamcorper sit. Ipsum dolor sit amet consectetur. Euismod
			elementum nisi quis eleifend quam adipiscing vitae proin. A scelerisque purus semper eget duis
			at tellus at. Habitant morbi tristique senectus et netus et. Sed cras ornare arcu dui vivamus.
			Tristique et egestas quis ipsum.
		</p>
		<h3 style={headingStyle}>Example Heading 3</h3>
		<p style={paragraphStyle}>
			Dui id ornare arcu odio ut sem nulla. Pretium aenean pharetra magna ac placerat vestibulum
			lectus. Morbi leo urna molestie at elementum eu. Hac habitasse platea dictumst vestibulum
			rhoncus est pellentesque elit. Ullamcorper eget nulla facilisi etiam dignissim diam quis.
			Sociis natoque penatibus et magnis dis parturient montes. Pellentesque diam volutpat commodo
			sed egestas egestas fringilla phasellus. Augue lacus viverra vitae congue eu consequat ac.
			Diam vulputate ut pharetra sit amet. Vulputate odio ut enim blandit volutpat maecenas volutpat
			blandit.
		</p>

		<h4 style={headingStyle}>Italics</h4>
		<p style={paragraphStyle}><em>The quick brown fox jumps over the lazy dog.</em></p>

		<h4 style={headingStyle}>Bold</h4>
		<p style={paragraphStyle}><b>The quick brown fox jumps over the lazy dog.</b></p>
	</div>

	<div class="column right">
		<!-- configure headings -->
		<div>
			<h3>Customize Headings</h3>
			<!-- font -->
			<div>
				<label for="heading-font-select">Choose a font for your headings:</label>
				<select id="heading-font-select" bind:value={selectedHeadingFont}>
					{#each headingFontOptions as hFont}
						<option value={hFont}>
							{hFont}
						</option>
					{/each}
				</select>
			</div>

			<!-- color -->
			<div>
				<label for="heading-color-select">Choose a color for your headings:</label>
				<select id="heading-color-select" bind:value={selectedHeadingColor}>
					{#each headingColorOptions as hColor}
						<option value={hColor}>
							{hColor}
						</option>
					{/each}
				</select>
			</div>
		</div>

		<!-- configure paragraphs -->
		<div>
			<h3>Customize Paragraphs</h3>
			<!-- font -->
			<div>
				<label for="paragraph-font-select">Choose a font for your paragraphs:</label>
				<select id="paragraph-font-select" bind:value={selectedParagraphFont}>
					{#each paragraphFontOptions as pFont}
						<option value={pFont}>
							{pFont}
						</option>
					{/each}
				</select>
			</div>

			<!-- color -->
			<div>
				<label for="paragraph-color-select">Choose a color for your paragraphs:</label>
				<select id="paragraph-color-select" bind:value={selectedParagraphColor}>
					{#each paragraphColorOptions as pColor}
						<option value={pColor}>
							{pColor}
						</option>
					{/each}
				</select>
			</div>
		</div>

		<!-- configure background -->
		<div>
			<h3>Customize Background</h3>
			<!-- color -->
			<div>
				<label for="background-color-select">Choose a color for your background:</label>
				<select id="background-color-select" bind:value={selectedBackgroundColor}>
					{#each backgroundColorOptions as bgColor}
						<option value={bgColor}>
							{bgColor}
						</option>
					{/each}
				</select>
			</div>
		</div>

		<div>
			<h4>CSS For This Theme:</h4>
			<pre><code>{theme}</code></pre>
		</div>
	</div>
</div>

<style>
	.row {
		display: flex;
	}

	.column {
		padding: 15px;
	}

	.left {
		flex: 60%;
	}

	.right {
		flex: 40%;
	}
</style>
