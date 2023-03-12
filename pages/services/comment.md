---
layout: page
title: Comment service
permalink: /services/comment
---

<p>
    Listens for comment objects sent by the <a href="/services/dispatcher">dispatcher</a> via an API endpoint and saves them to the <a href="/services/database">database</a>
</p>
<div class="features">
    <article>
        <span class="icon fa-github"></span>
        <div class="content">
            <h3>Repository</h3>
            <p><a href="https://github.com/flam-flam/comment-service">comment-service</a></p>
        </div>
    </article>
    <article>
        <span class="icon fa-code"></span>
        <div class="content">
            <h3>Language</h3>
            <p><a href="https://nodejs.org/en/docs/">NodeJS</a></p>
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
            <pre><code>curl -X GET http://localhost:8000/</code></pre>
            <pre><code>curl -X POST \
http://localhost:8000/api/comments \
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
                <li>Healthcheck:</li>
                <ul style="list-style-type: none">
                    <li><code>GET /</code></li>
                </ul>
                <li>Comment objects:</li>
                <ul style="list-style-type: none">
                    <li><code>POST /api/comments</code></li>
                </ul>
            </ul>     
        </div>
    </article>
    <article>
        <span class="icon fa-file-text"></span>
        <div class="content">
            <h3>Configuration</h3>
            <p>Port: 8000</p>
        </div>
    </article>
</div>
