<script>
	import jsonData from '$lib/labor.json';
</script>

<main>
	<h1>{jsonData.Personal_Details.Name}</h1>
	<section id="personal-details">
		<h2>Personal Details</h2>
		<p>
			Email: <a target="_blank" href="mailto:{jsonData.Personal_Details.Email}"
				>{jsonData.Personal_Details.Email}</a
			>
		</p>
		<p>
			LinkedIn: <a target="_blank" href={jsonData.Personal_Details.LinkedIn}
				>{jsonData.Personal_Details.LinkedIn}</a
			>
		</p>
	</section>
	<section id="description">
		<h2>About me</h2>
		<p>{jsonData.Intro}</p>
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

	<section id="skills">
		<h2>Skills</h2>
		<p><i>Programming Languages and Frameworks:</i> {jsonData.Skills.Programming_Languages.join(', ')}</p>
		<p><i>Tools and Environments:</i> {jsonData.Skills.Tools_and_Environments.join(', ')}</p>
		<p><i>Soft Skills:</i> {jsonData.Skills.Soft_Skills.join(', ')}</p>
	</section>

	<section id="languages">
		<h2>Languages</h2>
		<ul>
			{#each jsonData.Languages as language}
				<li>
					<strong>{language.Language}</strong><br />
					{language.Proficiency}<br />
				</li>
			{/each}
		</ul>
	</section>
</main>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Bitter:ital,wght@0,100..900;1,100..900&display=swap');
	@import url('https://fonts.googleapis.com/css2?family=DM+Mono:ital,wght@0,300;0,400;0,500;1,300;1,400;1,500&family=M+PLUS+1+Code:wght@100..700&display=swap');
	:root {
		--margin: 2rem;
		--double-margin: 3rem;
		--half-margin: 0.5rem;
		--mini-margin: 0.25rem;
		--space: 1rem;
		--line-hg: 1.5;
	}
	h1,
	h2 {
		font-family: 'DM Mono', Tahoma, Geneva, Verdana, sans-serif;
	}
	h2 {
		border-left: var(--margin) solid aquamarine;
		padding-left: var(--half-margin);
		width: fit-content;
	}
	main:not(h1, h2) {
		margin: var(--double-margin) var(--margin);
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
		text-align: justify;
		line-height: var(--line-hg);
		margin: 0;
	}
	a,
	a:visited {
		color: darkblue;
	}
</style>
