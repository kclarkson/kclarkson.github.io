<h1>Kaleem Clarkson's Personal Website</h1>

<p>The personal portfolio for Kaleem Clarkson's build with Sculpin, SASS and Bootstrap.</p>

<p>Sculpin is a static site generator written in PHP. It converts Markdown files, Twig templates or standard HTML into a static HTML site that can be easily deployed.</p>

<p>For more information visit <a href="https://sculpin.io/">Sculpin</a></p>

<h1>Site Reminders and Code</h1>

<p>used to generate the production sculpin output along with url
sculpin generate --env=prod --url=kclarkson/kclarkson.github.io</p>

<h1>Sculpin Blog Skeleton</h1>

<p>A skeleton for a Sculpin based blog.</p>

<p>Powered by <a href="http://sculpin.io">Sculpin</a>. =)</p>

<h2>Features</h2>

<p>A very basic Sculpin based blog supporting the following features:</p>

<ul>
<li>Very minimal Bootstrap based theme.</li>
<li>A handful of existing posts in <code>source/_posts/</code> to get you started. Feel
free to remove these when you are ready.</li>
<li>An about page at <code>/about</code>.</li>
<li>An index page at <code>/</code>. It displays all posts and paginates them.</li>
<li>A blog archive page at <code>/blog</code>. It displays post titles broken down by
month and is paginated.</li>
<li>A blog categories page at <code>/blog/categories</code>.</li>
<li>A blog category index at <code>/blog/categories/$category</code>. Similar to the blog
archive except broken down by each category.</li>
<li>A blog tags page at <code>/blog/tags</code>.</li>
<li>A blog tag index at <code>/blog/tags/$tag</code>. Similar to the blog archive
except broken down by each tag.</li>
</ul>

<h2>Build</h2>

<h3>If You Already Have Sculpin</h3>

<pre><code>sculpin install
sculpin generate --watch --server
</code></pre>

<p>Your newly generated clone of sculpin-blog-skeleton is now
accessible at <code>http://localhost:8000/</code>.</p>

<h3>If You Need Sculpin</h3>

<pre><code>curl -O https://download.sculpin.io/sculpin.phar
php sculpin.phar install
php sculpin.phar generate --watch --server
</code></pre>

<h2>Previewing Development Builds</h2>

<p>By default the site will be generated in <code>output_dev/</code>. This is the location
of your development build.</p>

<p>To preview it with Sculpin's built in webserver, run either of the following
commands. This will start a simple webserver listening at <code>localhost:8000</code>.</p>

<h3>Using Sculpin's Internal Webserver</h3>

<h4>Generate Command</h4>

<p>To serve files right after generating them, use the <code>generate</code> command with
the <code>--server</code> option:</p>

<pre><code>sculpin generate --server
</code></pre>

<p>To listen on a different port, specify the <code>--port</code> option:</p>

<pre><code>sculpin generate --server --port=9999
</code></pre>

<p>Combine with <code>--watch</code> to have Sculpin pick up changes as you make them:</p>

<pre><code>sculpin generate --server --watch
</code></pre>

<h5>Server Command</h5>

<p>To serve files that have already been generated, use the <code>serve</code> command:</p>

<pre><code>sculpin serve
</code></pre>

<p>To listen on a different port, specify the <code>--port</code> option:</p>

<pre><code>sculpin serve --port=9999
</code></pre>

<h3>Using a Standard Webserver</h3>

<p>The only special consideration that needs to be taken into account for standard
webservers <strong>in development</strong> is the fact that the URLs generated may not match
the path at which the site is installed.</p>

<p>This can be solved by overriding the <code>site.url</code> configuration option when
generating the site.</p>

<pre><code>sculpin generate --url=http://my.dev.host/blog-skeleton/output_dev
</code></pre>

<p>With this option passed, <code>{{ site.url }}/about</code> will now be generated as
<code>http://my.dev.host/blog-skelton/output_dev/about</code> instead of <code>/about</code>.</p>

<h2>Publishing Production Builds</h2>

<p>When <code>--env=prod</code> is specified, the site will be generated in <code>output_prod/</code>. This
is the location of your production build.</p>

<pre><code>sculpin generate --env=prod
</code></pre>

<p>These files are suitable to be transferred directly to a production host. For example:</p>

<pre><code>sculpin generate --env=prod
rsync -avze 'ssh -p 999' output_prod/ user@yoursculpinsite.com:public_html
</code></pre>

<p>In fact, <code>publish.sh</code> is provided to get you started. If you plan on deploying to an
Amazon S3 bucket, you can use <code>s3-publish.sh</code> alongside the <code>s3cmd</code> utility (must be
installed separately).</p>
