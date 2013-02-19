## WTF? ##

This is a clone of the old Slackworks Blarg.  The content was reanimated from what was visible
in the Wayback Machine.  The old system was custom code, ported from Merb to Rails, that kept
the articles in CouchDB.  The new one is just Octopress with an ugly skin on it.

## How to Use ##

The articles live in `source/_posts/`, they can be HTML or Markdown and just need some magic
Jekyll "front matter" YAML at the top so that Octopress knows what to do with them.  For the
old articles I put a permalink in, so make sure existing links worked.  But for new articles
you could just leave that off and let it autogenerate one from the title.

When trying it out locally, use `rake preview` to boot a little development instance.

## How it is deployed ##

This site has been configured to deploy using the Octopress Buildpack for Heroku.

https://github.com/jgarber/heroku-buildpack-ruby-octopress

Most crucially, this means that if you want to deploy it, you must set the BUILDPACK_URL:

`heroku config:add BUILDPACK_URL=git://github.com/jgarber/heroku-buildpack-ruby-octopress.git`

This can also be done at creation time with the `--buildpack=` argument to `heroku apps:create`
