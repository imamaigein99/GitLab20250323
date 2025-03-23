---


---

<h1 id="print-usernames-and-home-directories-in-linux">1. Print Usernames and Home Directories in Linux</h1>
<p>Write a Ruby or Bash script that prints usernames of all users on a Linux system along with their home directories. Example output:</p>
<pre><code>gitlab:/home/gitlab
nobody:/nonexistent
...

</code></pre>
<h3 id="bash-script"><strong>Bash Script</strong></h3>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token shebang important">#!/bin/bash</span>

<span class="token comment"># Loop through each line in /etc/passwd</span>
<span class="token keyword">while</span> IFS<span class="token operator">=</span>: <span class="token function">read</span> -r username _ _ _ _ home_dir _<span class="token punctuation">;</span> <span class="token keyword">do</span>
    <span class="token comment"># Print the username and home directory</span>
    <span class="token keyword">echo</span> <span class="token string">"<span class="token variable">$username</span>:<span class="token variable">$home_dir</span>"</span>
<span class="token keyword">done</span> <span class="token operator">&lt;</span> /etc/passwd

</code></pre>
<h3 id="explanation"><strong>Explanation</strong></h3>
<p>/etc/passwd is the file that holds and stores details about user accounts. It stores and holds certain information like Home Directory, User Ids, group Ids, usernames e.t.c, The script is just looking through the file and looping through each line to extract the details and print it in the terminal.</p>
<p>You can achieve the same using <code>awk</code> or <code>grep</code>, as shown below:</p>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token function">cat</span> /etc/passwd <span class="token operator">|</span> <span class="token function">awk</span> -F: <span class="token string">'{print <span class="token variable">$1</span> ":" <span class="token variable">$6</span>}'</span>

</code></pre>
<hr>
<h1 id="git-commit-graph-commands">2. Git Commit Graph Commands</h1>
<p>We have sent you an image named <code>git_history.v3.png</code> showing a Git commit graph. Below is a sequence of Git commands that could have produced the depicted commit graph:</p>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token comment"># 1. Initialize a Git repository</span>
<span class="token function">git</span> init

<span class="token comment"># 2. Create the first commit</span>
<span class="token keyword">echo</span> <span class="token string">"First commit"</span> <span class="token operator">&gt;</span> code.txt
<span class="token function">git</span> add code.txt
<span class="token function">git</span> commit -m <span class="token string">"first commit"</span>

<span class="token comment"># 3. Create the second commit</span>
<span class="token keyword">echo</span> <span class="token string">"Second commit"</span> <span class="token operator">&gt;&gt;</span> code.txt
<span class="token function">git</span> commit -am <span class="token string">"second commit"</span>

<span class="token comment"># 4. Create a new feature branch</span>
<span class="token function">git</span> checkout -b feature-branch

<span class="token comment"># 5. Add a feature commit on the new branch</span>
<span class="token keyword">echo</span> <span class="token string">"Awesome feature"</span> <span class="token operator">&gt;&gt;</span> feature_code.txt
<span class="token function">git</span> add feature_code.txt
<span class="token function">git</span> commit -am <span class="token string">"awesome feature"</span>

<span class="token comment"># 6. Switch back to the main branch</span>
<span class="token function">git</span> checkout main

<span class="token comment"># 7. Add a third commit on the main branch</span>
<span class="token keyword">echo</span> <span class="token string">"Third commit"</span> <span class="token operator">&gt;&gt;</span> code.txt
<span class="token function">git</span> commit -am <span class="token string">"third commit"</span>

<span class="token comment"># 8. Merge the feature branch</span>
<span class="token function">git</span> merge feature-branch -m <span class="token string">"Merge feature branch"</span>

<span class="token comment"># 9. Add a fourth commit on the main branch</span>
<span class="token keyword">echo</span> <span class="token string">"Fourth commit"</span> <span class="token operator">&gt;&gt;</span> code.txt
<span class="token function">git</span> commit -am <span class="token string">"fourth commit"</span>

</code></pre>
<hr>
<h1 id="git-the-ultimate-version-control-and-code-collaboration-tool">3. <strong>Git: The Ultimate Version Control and Code Collaboration Tool</strong></h1>
<p>Git is an important tool in today’s Agile software environment that aids collaboration, change tracking, and effective code management. Git guarantees that your code is always well-structured, safe, and manageable, regardless of whether you’re working alone on a personal project, remotely or with a large technical team.</p>
<h2 id="what-is-git"><strong>What is Git?</strong></h2>
<p>Git is a distributed version control system (DVCS) that lets a team work together without causing unsolvable conflicts, track changes in their code-base, and roll back to earlier iterations. Because of its dependability, speed, and flexibility, Git which was developed by Linus Torvalds in 2005, has emerged as the industry standard for version management.</p>
<blockquote>
<p><em>(Reference: Pro Git Book by Scott Chacon &amp; Ben Straub, Open Source)</em></p>
</blockquote>
<h3 id="key-features-of-git"><strong>Key Features of Git</strong></h3>
<ul>
<li><strong>Version Control</strong>: Track all changes in your project and revert if necessary.</li>
<li><strong>Smooth Collaboration</strong>: Multiple individuals can contribute without interfering with each other’s work.</li>
<li><strong>Distributed Development</strong>: Everyone has a full copy of the repository, enabling redundancy and offline work.</li>
<li><strong>Branching and Merging</strong>: Create separate branches for bug fixes, experiments, or new features, then merge them seamlessly.</li>
<li><strong>CI/CD Integration (Continuous Integration/Deployment)</strong>:<br>
Git integrates easily with CI/CD tools like <strong>GitLab CI/CD</strong>, as well as <strong>Infrastructure as Code (IaC)</strong> tools such as <strong>Terraform</strong> and <strong>Ansible</strong>. It also works with automation scripts to streamline deployment and testing, ensuring faster and more reliable software delivery to the market.</li>
</ul>
<h2 id="git--gitlab-a-perfect-match"><strong>Git + GitLab: A Perfect Match</strong></h2>
<p>GitLab offers a robust DevOps platform with integrated CI/CD, issue tracking, and project management capabilities, while Git offers version control. Teams can expedite software delivery, enhance code quality, and automate processes all in one location using GitLab.</p>
<h2 id="the-role-of-git-in-today’s-world"><strong>The Role of Git in Today’s World</strong></h2>
<p>Learning Git will increase your productivity and teamwork abilities, regardless of your level of experience as a developer. Are you prepared to use Git’s power? Explore GitLab and begin creating the software of the future right now!</p>
<hr>
<h1 id="debugging-a-ussd-service-issue-on-pilot.">4. Debugging a USSD Service Issue on pilot.</h1>
<h2 id="the-problem"><strong>The Problem</strong></h2>
<p>I work for a company that provides USSD service (<strong>Unstructured Supplementary Service Data)</strong>. It is a protocol used by mobile phones to communicate with the service provider’s system. Recently, we encountered an issue where some customers were unable to use a specific USSD code hosted for certain banks on our pilot environment. I picked up the ticket and prioritized it.</p>
<h2 id="investigation-and-debugging-steps"><strong>Investigation and Debugging Steps</strong></h2>
<ol>
<li>
<p><strong>Checked Logs with ELK (Elasticsearch, Logstash, Kibana)</strong></p>
<ul>
<li>Verified that the core USSD application was <strong>active and receiving traffic</strong>.</li>
<li>On the downstream system, i found <strong>database-related errors</strong> in the logs.</li>
</ul>
</li>
<li>
<p><strong>Analyzed Metrics in Grafana</strong></p>
<ul>
<li>Observed error patterns matching those found in ELK logs.</li>
</ul>
</li>
<li>
<p><strong>Restarted the Application on Node 1</strong></p>
<ul>
<li>Found that it <strong>could not connect to KeyDB (our database)</strong>.</li>
<li>Checked the <strong>KeyDB server</strong> and discovered <strong>disk space was full</strong>.</li>
</ul>
</li>
<li>
<p><strong>Examined KeyDB Logs</strong></p>
<ul>
<li>Confirmed <strong>storage-related failures</strong> as the root cause.</li>
</ul>
</li>
</ol>
<h2 id="the-fix"><strong>The Fix</strong></h2>
<ol>
<li>
<p>Used <strong>GitLab CI/CD pipeline</strong> to provision <strong>additional disk space</strong> across all three KeyDB nodes.</p>
</li>
<li>
<p>Flushed the database using:</p>
<pre class=" language-bash"><code class="prism  language-bash">docker <span class="token function">exec</span> -it keydb-keydb-1 keydb-cli -a <span class="token punctuation">{</span>password<span class="token punctuation">}</span> FLUSHALL

</code></pre>
</li>
<li>
<p><strong>Applied necessary KeyDB configurations</strong> and restarted the service.</p>
</li>
<li>
<p>Restarted the USSD application to ensure proper connectivity.</p>
</li>
<li>
<p>Monitored logs and verified that errors were <strong>significantly reduced</strong>.</p>
</li>
<li>
<p>Confirmed successful resolution with test cases.</p>
</li>
</ol>
<h2 id="preventing-future-occurrences"><strong>Preventing Future Occurrences</strong></h2>
<ul>
<li><strong>Automated Disk Space Cleanup:</strong> Implemented scheduled database flushing.</li>
<li><strong>Grafana Alerts:</strong> Set up <strong>email &amp; SMS notifications</strong> for low disk space.</li>
<li><strong>Documentation:</strong> Created a <strong>knowledge base article</strong> on <strong>Confluence</strong> detailing the issue and resolution.</li>
</ul>
<h2 id="the-outcome"><strong>The Outcome</strong></h2>
<p>By leveraging <strong>ELK, Grafana, and GitLab CI/CD</strong>, I was able to <strong>quickly diagnose and resolve the issue</strong>, restoring service availability and improving customer experience.</p>
<hr>

