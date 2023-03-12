---
layout: page
title: Dispatcher service
permalink: /services/dispatcher
---

<p>
    Streams submissions and comments from Reddit and forwards the json objects to the respective endpoints
</p>
<div class="features">
    <article>
        <span class="icon fa-github"></span>
        <div class="content">
            <h3>Repository</h3>
            <p><a href="https://github.com/flam-flam/dispatcher-service">dispatcher-service</a></p>
        </div>
    </article>
    <article>
        <span class="icon fa-code"></span>
        <div class="content">
            <h3>Language</h3>
            <p><a href="https://docs.python.org/3/">Python</a></p>
        </div>
    </article>
    <article>
        <span class="icon fa-rocket"></span>
        <div class="content">
            <h3>Releases</h3>
            <p>
                <ul>
                    <li><a href="https://github.com/flam-flam/dispatcher-service/releases/tag/0.3.0">0.3.0</a></li>
                    <li><a href="https://github.com/flam-flam/dispatcher-service/releases/tag/0.2.0">0.2.0</a></li>
                    <li><a href="https://github.com/flam-flam/dispatcher-service/releases/tag/0.1.0">0.1.0</a></li>
                </ul>
            </p>
        </div>
    </article>
    <article>
        <span class="icon fa-terminal"></span>
        <div class="content">
            <h3>Usage</h3>
            <p>Using your Reddit account, create new app credentials, to allow the service to retrieve the data</p>
        </div>
    </article>
    <article>
        <span class="icon fa-paper-plane"></span>
        <div class="content">
            <h3>Endpoints</h3>
            <p>Outbound:</p>
            <ul>
                <li><a href="/services/sumission">Submission service</a>:</li>
                <ul style="list-style-type: none">
                    <li><code>POST /api/submissions</code></li>
                </ul>
                <li><a href="/services/comment">Comments</a>:</li>
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
            <ul>
                <li>Debug: false</li>
                <li>Subreddits: all</li>
            </ul>
        </div>
    </article>
</div>
