<script>
	import jsonData from '$lib/labor.json';
</script>

<main>
	<h1>{jsonData.Personal_Details.Name}</h1>
	<section id="personal-details">
		<h2>Personal Details</h2>
		<p>Identity Document: {jsonData.Personal_Details.Identity_Document}</p>
		<p>Place and Date of Birth: {jsonData.Personal_Details.Place_and_Date_of_Birth}</p>
		<p>Phone: <a target="_blank" href="tel:+573204388563">{jsonData.Personal_Details.Phone}</a></p>
		<p>
			Email: <a target="_blank" href="mailto:{jsonData.Personal_Details.Email}">{jsonData.Personal_Details.Email}</a
			>
		</p>
		<p>
			LinkedIn: <a target="_blank" href={jsonData.Personal_Details.LinkedIn}
				>{jsonData.Personal_Details.LinkedIn}</a
			>
		</p>
	</section>

	<section id="education">
		<h2>Education</h2>
		<ul>
			{#each jsonData.Education as experience}
				<li>
					<strong>{experience.Degree}</strong><br />
					University: <u>{experience.University}</u><br />
					Year Obtained: {experience.Year_Obtained}
				</li>
			{/each}
		</ul>
	</section>

	<section id="work-experiences">
		<h2>Work Experiences</h2>
		<ul>
			{#each jsonData.Work_Experiences as experience}
				<li>
					<strong>{experience.Position}</strong> at <i>{experience.Company}</i><br />
					Period: <u>{experience.Period}</u><br />
					Description: {experience.Description}
				</li>
			{/each}
		</ul>
	</section>

	<section id="skills">
		<h2>Skills</h2>
		<p>Programming Languages and Frameworks: {jsonData.Skills.Programming_Languages.join(', ')}</p>
		<p>Tools and Environments: {jsonData.Skills.Tools_and_Environments.join(', ')}</p>
	</section>

	<section id="languages">
		<h2>Languages</h2>
		<ul>
			{#each jsonData.Languages as language}
				<li>
					Language: {language.Language}<br />
					Reading: {language.Reading}<br />
					Writing: {language.Writing}<br />
					Listening: {language.Listening}<br />
					Speaking: {language.Speaking}
				</li>
			{/each}
		</ul>
	</section>
</main>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Bitter:ital,wght@0,100..900;1,100..900&display=swap');
	:root {
		--margin: 2rem;
		--space: 1rem;
		--line-hg: 1.5;
	}
	h1,
	h2 {
		font-family: 'Cascadia Code', Tahoma, Geneva, Verdana, sans-serif;
	}
	main:not(h1, h2) {
		margin: var(--margin);
		font-family: 'Bitter', Cochin, Georgia, Times, 'Times New Roman', serif;
	}
	ul {
		display: flex;
		flex-direction: column;
		gap: var(--space);
		list-style-type: none;
		padding-left: 0;
	}
	p,
	li {
		line-height: var(--line-hg);
		margin: 0;
	}
	a,
	a:visited {
		color: darkblue;
	}
</style>
