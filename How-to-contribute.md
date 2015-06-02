Thanks for considering to contribute to this Wiki. Before contributing, please make sure you've read and understood the [[Wiki Rules]].

This Wiki is based on [Gollum](https://github.com/gollum/gollum), a [Git](http://git-scm.com/) based Wiki system. The markup language used is [Markdown](http://daringfireball.net/projects/markdown/syntax) in the [Github flavored](https://help.github.com/articles/github-flavored-markdown/) version.

[davwiki.org](http://davwiki.org) only serves the Wiki content, without any option to edit it. The sources of this Wiki are available at [github.com/dmfs/davwiki/wiki](https://github.com/dmfs/davwiki/wiki). All changes at GitHub will be pushed to http://davwiki.org on a regular base. At present this is a manual process, so it might take some time.

This Wiki uses custom templates and css not available on GitHub, which means that the presentation on GitHub will be different from the presentation on http://davwiki.org.

Please note that some files may contain `:` characters, which means that it's not possible to clone the repository on Windows.

To give the Wiki a consistent appearance, please follow the rules below:

### Use templates

The [[Templates|Templates/all]] page contains a number of templates. When adding a new page, pick the appropriate template and populate it with content and save it under the name name. When adding files with the special charactes `:`, clone the repository and create the file manually. If there is no appropriate template yet, consider to create one first.

### Content conventions

* Use the blockquote character `>` when adding quotes from an RFC.
* Always add references to the original RFC. Link the html version of the RFC at http://tools.ietf.org/html/rfcXXXX.
* Add deep links using anchors if possible (i.e. like http://tools.ietf.org/html/rfcXXXX#section-1.2).
* Github Flavored Markdown supports XML comments, i.e. `<!-- a comment is not visible in the rendered page -->`, use it if necessary
* Put the page title into a meta comment containing `--- title: PAGETILE` if it can't be derived from the file name.

### Filename conventions

* Pages of XML elements should be named after their fully qualified name like `<namespace>:<name>.md`
* If a file name would contain `/`, it should be replaced by `-`, like so `http:--calendarserver.org-ns-:getctag.md`
