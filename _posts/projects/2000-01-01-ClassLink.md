---
company: Columbia
project: Risk Communication
type: user interface & user experience
description: A home page resdesign integrating user localizatin for hurricane risk communication
categories: projects
layout: project-post
permalink: /projects/:title
img-preview: /assets/images/projects/columbia/preview.png
---

<h2>Kinetic - User Behavior Analytics</h2>

<span class="tools">Figma, React, Python, Mixpanel</span>

<div class="post-section">
<h3>Role</h3>
<p class="role">Interviews, Survey, Ideation, Sketching, Prototyping, Evaluation, and Implementing</p>
</div>

<div class="post-section">
<h3>Background</h3>
<p>Kinetic focuses on crafting worker-safety devices, accompanied with a dashboard for managers. Around this period, Kinetic was also in the process of rolling out a COVID-19 contract-tracing tool feature into the dashboard, so there was a demand to invest in understanding our users more. To solve this issue, we had to create a plan to better understand how users are interfacing with the dashboard.</p>
<p><img class="centered-image" src="/assets/images/projects/kinetic/portfolio/4.png" /></p>

</div>

<div class="post-section">
<h3>Design Questions</h3>
<p class="emphasize-paragraph">How could we determine when users are experiencing difficulty navigating the dashboard? Who needs help the most? When a user interface anomaly appears, is this an isolated or universal event? Which features are used the least?</p>
</div>

<div class="post-section">
<h3>Research Findings</h3>
<ul class="research-findings">
	<li>Managers check their dashboard the most during the start and end of the week.</li>
	<li>Users who are already engaged with our customer engineers have the most activity.</li>
	<li>Whenever a user would use the contact-tracing feature, they would not change the default values, and repeatedly search for the same individual.</li>
	<li>The week of onboarding reveals the most activity on the dashboard for most users, as well as periods when hardware anomalies were reported.</li>
</ul>
</div>

<div class="post-section">
<h3>Persona Development</h3>
<p>The existing users for the client dashboard are managers. However, since the contact-tracing feature was released, the user analytics had to account for two types of activities from the managers: contact-tracing and injury reduction. The events that would be implemented for tracking user behaviors would be based around these two personas.</p>
	<div class="personas">
		<div>
			<h2>Manager Concerned with Contact Tracing</h2>
			<img src="/assets/images/projects/kinetic/portfolio/5.png" />
			<p>“An employee told me they were feeling a little bit sick, so I need to find a way which employees he has been in contact with for the day.”</p>
		</div>
		<div>
			<h2>Manager Concerned with Injury Reduction</h2>
			<img src="/assets/images/projects/kinetic/portfolio/6.png" />
			<p>“An employee expressed that she is having trouble walking. I want to know if her physical ailment is improving.”</p>
		</div>
	</div>
</div>

<div class="post-section">
	<h3>Survey</h3>
	<p>
		The customer engineers are an extension of the product team. We constantly worked with them because they had a closer relationship to the users since they have often met with the clients face-to-face during the onboarding process. Before sketching out possible events, a survey was sent out to a few managers to gauge how they are interacting with the dashboard. Due to privacy concerns, these are not directly the questions, but they follow the same format and the direction of the inquiry.
	</p>
	<div class="highlight-chunk">
		<p>Sample Survey Questions</p>
		<p> On a scale of 1 to 5, 5 being the most, and 1 being the lowest, how frequent do you check the dashboard?</p>
		<p>On a scale of 1 to 5, 5 being the most, and 1 being the lowest, how often do you ask for help with navigating the dashboard?</p>
	</div>
	<p>These types of questions would give me a general understanding of which users are active in the first place, and this could help with the accuracy of the analytics report. If any mismatches exist between the survey and the analytics report, then we could isolate that user and check the status of their setup.</p>
</div>

<div class="post-section">
	<h3>Interviews</h3>
	<p>Along with surveys, interviews were conducted with the clients. The customer engineer and the product team would schedule a time to follow-up with the survey since the survey does not necessarily provide a nuanced information. Users are more likely to explain more information because they are given the platform to discuss their thoughts. In this process, we would similarly ask the same questions we did the on the survey regarding the usability of the dashboard.</p>
	<p>
		Users who were concerned with injury reduction would often highlight user interface consistency or inconsistency on the data analytics page, since this is where managers could filter out parameters to check the level of injury reduction. This means, more user analytic events would be added on this page.
	</p>	
</div>

<div class="post-section">
	<h3>Ideation</h3>
	<p>
		Overall, there were two important parts to track: short-term and long-term behavioral goals. In the first iteration, there were based on user interface and user behavior goals. After reviewing the surveys and interviews more, users have expressed their long-term objectives related to seeing the injury reduction increase, while their short-term objectives usually involved usability heuristics, such as visibility of system status (e.g. a tool-tip explanation attached to input titles). 
	</p>
	<h2>
	</h2>
	<div class="highlight-chunk">
		<p>Base Framework for Tracking User Behavior Analytics</p>
		<p>1. Establish a product goal</p>
		<p>2. Separate between short-term and long-term goals</p>
		<p>3. Create and attach a flow for each goal</p>
		<p>4. Determine events that would constitute a flow</p>
	</div>
	<p>
		Since there was no existing framework, with this in mind, I drafted a general base for tracking user behavior analytics that can be extended to other products, not just the client dashboard. I used the qualitative data from the interviews and surveys to determine how to organize events through Mixpanel. 
	</p>
	<p>
		Mixpanel was chosen because this fit the budget of the company and the onboarding was quick, but there were also limitations I had to consider while choosing this platform. For example, the user could only be tracked if the user first logs in. If the user closes the browser, but the cookies are saved, the session tracking would produce undefined data, which has <a href="https://community.mixpanel.com/data-management-10/problem-with-anonymous-user-login-and-register-542">not been fixed</a> as of yet.	
	</p>
	<p>
		After I sketched the base framework, I shared this with the product team. We all agreed that the framework is a good base to start specifying events for the client dashboard.
	</p>
	<p><img class="centered-image" src="/assets/images/projects/kinetic/portfolio/8.png" /></p>
</div>

<div class="post-section">
	<h3>Prototyping</h3>
	<p>For the prototype, I took a screenshot of the current “Team” page which receives the most action based on the surveys and interviews. And then, I started marking areas where events could be added. At first, I thought that adding events on everything would make sense because this gives so much more flexibility for tracking a user flow, but with the scope of the project and based on the time limitation, I had to be a bit more deliberate about which elements would be ascribed an event on Mixpanel.</p>
	<p><img class="centered-image" src="/assets/images/projects/kinetic/portfolio/10.png" /></p>
	<p>
		Each name of the event is broken down to “location”, “type of action”, and “component” but there could be events that do not take up a tangible space such as a button or an input field because they happen in the background, like the first event which detects page arrival.
	</p>
	<div class="highlight-chunk">
		<p>Events for Team Page</p>
		<p>1) Team employees tab - page arrival<br>properties: email, location, total workers</p>
		<p>2) Team employees tab - tab pressed - employees<br>properties: email, location</p>
		<p>3) Team employees tab - tab pressed - add employees<br>properties: email, location </p>
		<p>4) Team employees tab - tab pressed - group <br>properties: email, location </p>
		<p>5) Team employees tab - field changed - search employees<br>properties: email, location, employee</p>
		<p>6) Team employees tab - field changed - group select <br>properties: email, location, group</p>
		<p>7) Team employees tab - field changed - assignment select<br>properties: email, location, assignment</p>
		<p>8) Team employees tab - button activated - add employee<br>properties: email, location</p>
		<p>9) Team employees tab - field changed - select all employees<br>properties: email, location </p>
		<p>10) Team employees tab - field changed - name<br>properties: email, location, sort</p>
		<p>11) Team employees tab - field changed - group<br>properties: email, location, sort </p>
		<p>12) Team employees tab - field changed - assignment<br>properties: email, location, sort </p>
		<p>13) Team employees tab - button activated - table row settings<br>properties: email, location, employee, group, assignment </p>
		<p>14) Team employees tab - field changed - table row employee<br>properties: email, location, employee, group, assignment </p>
	</div>
	<p>
		Based on the events listed above, one short-term goal would be “weekly frequency of use”, which would include “Team employees tab - page arrival” as the main source of the goal. The definition of “use” is vague because this does not specify how did the user interact with the product. Thus, this short-term goal is based on the arrival of the user on the page, rather than their specified interactions. A more specified goal would be “onboarding employees” which would attach events that would include adding employees to the roster.
	</p>
</div>

<div class="post-section">
	<h3>Results</h3>
	<p>
		The result of the events led to a weekly report for each client. The client’s name is not provided due to privacy concern but this is a sample of their activity on the contract tracing tool. Separate from the team page, the contact tracing tool also received a set of events similar to the ones shown above, but due to intellectual property concern, I am not advised to share the process of that interface. With this data, the product team could keep note of behaviors and patterns of users based on their interaction.
	</p>
	<p><img class="centered-image" src="/assets/images/projects/kinetic/portfolio/11.png" /></p>
</div>

<div class="post-section">
	<h3>Lessons Learned</h3>
	<div class="highlight-chunk">
		<p>Further Notes</p>
		<p>Mixpanel has limitations, and so do other analytics platform, instead a platform should be picked based on the currnet needs of the product. Some companies have shorter sprints and missions.</p>
		<p>Quantitative results should be backed by qualitiative research. Follow-ups through interviews and surveys can strengten the exisitng data.</p>
		<p>Do not attach events to all components because that would create more data that may be unnecessary  to the larger picture.</p>
	</div>
</div>