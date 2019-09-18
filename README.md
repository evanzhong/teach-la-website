# Teach LA Website

[![Build Status](https://travis-ci.com/uclaacm/teach-la-website.svg?branch=master)](https://travis-ci.com/uclaacm/teach-la-website)

Heya there, this is a work-in-progress website for ACM Teach LA! It's goal is to give Teach LA a more formal online presence, and to create a one-stop shop for prospective tutors and schools to get more information about us!

This website is built with [Jekyll](https://jekyllrb.com), with some component implementations taken from [ACM's main website](https://github.com/uclaacm/website) (conforming to [ACM Design's Style Guide](https://github.com/uclaacm/Styleguide)). We build this website with Travis CI (and plan to add some `rake` testing soon), and deploy it on GitHub Pages.

*Note:* we've elected to use Travis to auto-build and deploy to GitHub Pages rather than use the `github-pages` gem. This allows us a bit more fine-tuning in exactly what is deployed, and allows for more modularity in the future!

## Development Setup

To get a copy of this website running locally on your machine, you'll need [Ruby](https://www.ruby-lang.org/en/), a copy of this repo, and access to your system's shell/terminal.

*Note:* we recommend using [rvm](https://rvm.io/) instead of your system ruby; it makes life easier :smile:!

First, let's install [Bundler](https://bundler.io/), a gem environment manager for ruby. Type this anywhere in your shell:

```bash
gem install bundler
```

Then, inside our project, run

```bash
bundle
```

This should install all of our RubyGems dependencies! Note that we've committed a `Gemfile.lock`, so you should get a working set of gems.

Finally, run:

```bash

$ bundle exec jekyll serve
Configuration file: /Users/malsf21/code/teach-la-website/_config.yml
            Source: /Users/malsf21/code/teach-la-website
       Destination: /Users/malsf21/code/teach-la-website/_site
 Incremental build: disabled. Enable with --incremental
      Generating... 
                    done in 0.219 seconds.
 Auto-regeneration: enabled for '/Users/malsf21/code/teach-la-website'
    Server address: http://127.0.0.1:4000/teach-la-website/
  Server running... press ctrl-c to stop.

```

Visit whatever follows the server address line in your browser, which is usually [http://127.0.0.1:4000/teach-la-website/](http://127.0.0.1:4000/teach-la-website/).

If you run into any issues, please let us know on our [issues tracker](https://github.com/uclaacm/teach-la-website)!

## Adding Yourself to the Teams Page

Are you a member of ACM Teach LA? You should add yourself to our teams page, so we can show you off to all of the schools we teach!

Each individual profile is generated by Jekyll from the data found in `_data/team.yml`. If you open it up, you'll find sets of objects that look like this:

```yaml
mwang:
  name: "Matt Wang"
  title: "Dev Team Director"
  img: mwang.jpg # semi-optional!
```

If you want to add yourself, all you need to do is add a top-level object with your information, and a photo! Drop your photo in `img/team/`.

Things to keep in mind:
* your top-level key must be unique! make sure that nobody else has it!
* `name` and `title` are mandatory!
* `img` is semi-optional: if you don't include it, we'll render a random image from [adorable avatars](http://avatars.adorable.io/). While it doesn't break the site, it's not ... super professional. A photo would be great!
* the `img` key's value should be the name of your image file; not the absolute path!

Once you think you're ready, commit all of your changes and send a PR our way. We should get you up and running in no time!
