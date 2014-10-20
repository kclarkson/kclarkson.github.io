<h2>CSS Structure is based on the Drupal Omega Theme file structure mainly because it makes the most sense to me.</h2>

<p>Thanks to Fred Parke's for writing the best blog post I could find that explaines a good SASS file struction. Its a great read: http://www.fredparke.com/blog/get-aquainted-omegas-sass-file-structure</p>

<p>SASS file roadmap
sass/<br />
|
|- abstractions/             # Partials for custom mixins and extends.
|<br />
|- base/                     # Partials for base styles of raw HTML elements.
|  |-- _forms.scss<br />
|  |-- _lists.scss<br />
|  ...
|
|- components/               # Partials for individual components of your site.
|  |-- _navigation.scss<br />
|  |-- _search.scss<br />
|  ...
|
|- variables/                # Partials for sass variables.
|  |-- _colors.scss<br />
|  |-- _typography.scss<br />
|  ...
|
|- themename.hacks.scss      # Can be used for temporary hot-fixes.
|- themename.no-query.scss   # Re-renders themename.styles.scss without any media queries.
|- themename.normalize.scss  # Provides CSS reset based on the legacy variables.
|- themename.styles.scss     # Primary stylesheet aggregates the partials into a single file.</p>

<p>The import process
The themename.styles.scss file first imports the external libraries and then imports our partials.</p>

<p>@import "compass";
@import "breakpoint";
@import "singularitygs";
@import "toolkit-no-css";</p>

<p>@import "variables/<strong>/*";
@import "abstractions/</strong>/*";
@import "base/<strong>/*";
@import "components/</strong>/*";</p>

<p>The variables folder is imported first, and for good reason - all of your other sass files will likely need to access these variables.</p>

<p>You can see from the asterisks that sass globbing is being used - this is really handy, it means the sass files inside these folders (and any subfolders within them) will automatically be imported.</p>
