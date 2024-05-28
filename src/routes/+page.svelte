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
		{#each jsonData.Work_Experiences as experience}
			<p><strong>{experience.Position}</strong> at <i>{experience.Company}</i></p>
			<p>Period: <u>{experience.Period}</u></p>
			{#each experience.Description as respons}
				<ul>
					<li>{respons}</li>
				</ul>
			{/each}
		{/each}
	</section>

	<section id="education">
		<h2>Education</h2>
		<div class="mini-space">
			{#each jsonData.Education as experience}
				<div>
					<p><strong>{experience.Degree}</strong></p>
					<p>University: <u>{experience.University}</u> - {experience.Year_Obtained}</p>
				</div>
			{/each}
		</div>
	</section>

	<section id="skills">
		<h2>Skills</h2>
		<div class="mini-space">
			<p>
				<i>Programming Languages and Frameworks:</i>
				{jsonData.Skills.Programming_Languages.join(', ')}
			</p>
			<p><i>Tools and Environments:</i> {jsonData.Skills.Tools_and_Environments.join(', ')}</p>
			<p><i>Soft Skills:</i> {jsonData.Skills.Soft_Skills.join(', ')}</p>
		</div>
	</section>

	<section id="languages">
		<h2>Languages</h2>
		<div class="mini-space">
			{#each jsonData.Languages as language}
				<div>
					<p><strong>{language.Language}</strong></p>
					<p>{language.Proficiency}</p>
				</div>
			{/each}
		</div>
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
		border-left: var(--margin) solid rgb(151, 207, 253);
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
	}
	.mini-space {
		display: flex;
		flex-direction: column;
		gap: var(--half-margin);
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
