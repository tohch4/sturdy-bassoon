# sturdy-bassoon
An example website for explaining information security, application, and network security practices.

## Development

### Prerequisites

This prototype uses Docker to encapsulate development and deployment requirements for quicker prototyping.

You will need to install Docker version 19.03 or later on your Linux, macOS, or Windows workstation to proceed.

### Creating the Jekyll Site

NOTE: This step was created during project creation. This is for historical awareness you do not need to run this again.

The empty repository was cloned and the Jekyll CLI was to create the site scaffold.

```sh
$ git clone git@github.com:tohch4/sturdy-bassoon.git
$ cd sturdy-bassoon
$ docker run -v $(pwd):/app -it jekyll/jekyll:4.0 jekyll new /app
$ find .
.
./.README.md.swp
./_posts
./_posts/2020-12-30-welcome-to-jekyll.markdown
./index.markdown
./404.html
./README.md
./.gitignore
./about.markdown
./_site
./_site/feed.xml
./_site/jekyll
./_site/jekyll/update
./_site/jekyll/update/2020
./_site/jekyll/update/2020/12
./_site/jekyll/update/2020/12/30
./_site/jekyll/update/2020/12/30/welcome-to-jekyll.html
./_site/index.html
./_site/404.html
./_site/about
./_site/about/index.html
./_site/README.md
./_site/assets
./_site/assets/main.css.map
./_site/assets/main.css
./_site/assets/minima-social-icons.svg
./_config.yml
./Gemfile
./Gemfile.lock
```

### Testing the Site Locally on Your Workstation

You can build a new copy of the site and run it locally with the following Docker command.

```sh
$ cd sturdy-bassoon
$ docker run -p 4000:4000 -v $(pwd):/app -it -w /app jekyll/jekyll:4.0 bundle exec jekyll serve --host 0.0.0.0
Configuration file: /app/_config.yml
            Source: /app
       Destination: /app/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
       Jekyll Feed: Generating feed for posts
                    done in 0.864 seconds.
 Auto-regeneration: enabled for '/app'
    Server address: http://0.0.0.0:4000/
  Server running... press ctrl-c to stop.
```

If you see the last line, this means the Jekyll CLI is successfully started to serve a local copy of the site.

Visit [http://localhost:4000](http://localhost:4000) in your preferred web browser or click that link.

Thanks to the Docker filesystem mounting, you should be able to edit files and as they are saved, Jekyll will attempt to rebuild and reload the site for you.
```
