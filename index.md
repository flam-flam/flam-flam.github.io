---
layout: default
---

<!-- Banner -->
  <section id="banner">
    <div class="content">
      <header>
        <h1>Flamboyance of Flamingos</h1>
        <p>A set of fully observable microservices (WIP)</p>
      </header>
      <p>
        This is a pet project aimed to implement microservices with
        best (effort) practice observability.
        Four pillars of observability are to be implemented into the services,
        providing an open source demo implementation of metrics, events, logs,
        and traces into python, dotnet, and nodejs apps that run on k8s.
        Developed by a few enthusiasts in their spare time and
        is very much a work in progress for now.
      </p>
      <ul class="actions">
        <li><a href="https://github.com/flam-flam" class="button special">github <i class="fa fa-external-link"></i>
        </a></li>
      </ul>
    </div>
  </section>
  

<!-- Section -->
<section>
	<header class="major">
		<h2>Why?</h2>
	</header>
	The project is supposed to serve as a fully contained easily deployable demo of microservice observability. Want to see how it works on the dashboards? Sure. Want to rip some example code out to use in your project? You got it! The possibilities are... fairly limited.
</section>


<!-- Section -->
<section id="homepage-melt">
	<header class="major">
		<h2>What is MELT?</h2>
	</header>
	<p>
		MELT stands for Metrics, Events, Logs, and Traces, which are the 4 pillars of Observability.
		Some might tell you there are 3, but that is false, fight me. <a href="/melt">Read more</a>
	</p>
	<div class="features">
		<article>
			<span class="icon fa-line-chart"></span>
			<div class="content">
				<h3>Metrics</h3>
				<p>Time series of numeric aspect of a system or an application.</p>
			</div>
		</article>
		<article>
			<span class="icon fa-list"></span>
			<div class="content">
				<h3>Events</h3>
				<p>Discreet pieces of structured data that are emitted when something interesting happens.</p>
			</div>
		</article>
		<article>
			<span class="icon fa-file-text-o"></span>
			<div class="content">
				<h3>Logs</h3>
				<p>Pieces of readable text data that are normally used by software engineers.</p>
			</div>
		</article>
		<article>
			<span class="icon fa-link"></span>
			<div class="content">
				<h3>Traces</h3>
				<p>A hierarchical set of data that contains information about a path of a request as it follows a complex path through the whole system</p>
			</div>
		</article>
	</div>
</section>

<!-- Section -->
<section id="homepage-services">
	<header class="major">
		<h2>Services</h2>
	</header>
	<p>
		The microservices in this project are small and simple.
	</p>
	<div class="features">
		<article>
			<span class="icon fa-reddit-alien"></span>
			<div class="content">
				<h3><a href="/services/dispatcher">Reddit dispatcher</a></h3>
				<p>Stream submissions and comments from Reddit and forward the json objects to an endpoint. Written in Python.</p>
			</div>
		</article>
		<article>
			<span class="icon fa-comment"></span>
			<div class="content">
				<h3><a href="/services/submission">Submission service</a></h3>
				<p>Listen for json submission objects from the dispatcher service and save them to a database. Written in C#.</p>
			</div>
		</article>
		<article>
			<span class="icon fa-comments-o"></span>
			<div class="content">
				<h3><a href="/services/comment">Comment service</a></h3>
				<p>Listen for json comment objects from the dispatcher service and save them to a database. Written in NodeJS.</p>
			</div>
		</article>
		<article>
			<span class="icon fa-database"></span>
			<div class="content">
				<h3><a href="/services/database">MongoDB</a></h3>
				<p>A database to store the data. Submission and comment services connect to it.</p>
			</div>
		</article>
	</div>
</section>
