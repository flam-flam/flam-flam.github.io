---
layout: page
title: Submission service
permalink: /services/submission
---

<p>
    Listens for post submission objects sent by the <a href="/services/dispatcher">dispatcher</a> via an API endpoint and saves them to the <a href="/services/database">database</a>
</p>
<div class="features">
    <article>
        <span class="icon fa-github"></span>
        <div class="content">
            <h3>Repository</h3>
            <p><a href="https://github.com/flam-flam/submission-service">submission-service</a></p>
        </div>
    </article>
    <article>
        <span class="icon fa-code"></span>
        <div class="content">
            <h3>Language</h3>
            <p><a href="https://learn.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/">C#</a></p>
        </div>
    </article>
    <article>
        <span class="icon fa-rocket"></span>
        <div class="content">
            <h3>Releases</h3>
            <p>None yet...</p>
        </div>
    </article>
    <article>
        <span class="icon fa-terminal"></span>
        <div class="content">
            <h3>Usage</h3>
            <p><a href="http://localhost:5000/swagger/index.html">Swagger</a></p>
            <pre><code>curl -X GET http://localhost/api/submissions/{id}</code></pre>
            <pre><code>curl -X POST \
http://localhost/api/submissions \
-H 'Content-Type: application/json' \
-d '{"id":"1a", \
"created_utc":"2023-03-10T16:27:59.709Z"}'</code></pre>
        </div>
    </article>
    <article>
        <span class="icon fa-paper-plane"></span>
        <div class="content">
            <h3>Endpoints</h3>
            <p>Inbound:</p> 
            <ul>
                <li>Get submission by id:</li>
                <ul style="list-style-type: none">
                    <li><code>GET /api/submissions/{id}</code></li>
                </ul>
                <li>Post submission objects:</li>
                <ul style="list-style-type: none">
                    <li><code>POST /api/submissions</code></li>
                </ul>
            </ul>     
        </div>
    </article>
    <article>
        <span class="icon fa-file-text"></span>
        <div class="content">
            <h3>Configuration</h3>
            <ul>
                <li>LogLevel</li>
                <ul style="list-style-type: none">
                    <li>Default: Information</li>
                    <li>Microsoft.AspNetCore: Warning</li>
                </ul>
                <li>AllowedHosts: *</li>
            </ul>
        </div>
    </article>
</div>
