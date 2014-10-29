# DevOps Bootcamp Website & Curriculum

WWU Version hosted at [wwudevops.github.io/website][WWU DevOps Website].

OSU Version hosted at [devopsbootcamp.osuosl.org][OSU DevOps BootCamp].

This repository has a post-commit hook set up to update the main site every
time the master branch is changed. If the site doesn't update within a couple
of minutes, the build may have failed. Check that `make html` doesn't throw
any errors in your copy of the repo, and ask someone with admin access on
readthedocs to investigate what it reports is broken.

## Viewing Slides

Slides are available at [wwudevops.github.io/slides][WWU DevOps Slides], and
rebuilt automatically whenever new content is pushed to the master branch of
this repo.

The script in scripts/build.sh automatically removes the slides that were built
of non-slides content, based on the assumption that the filenames of all actual 
slides start with the week number.   

You can also build the slides locally if you've been editing them and want to
see how they'll look before you push, or if you don't have push access to the
project: 

## Installing Dependencies

### Debian and Ubuntu
```
sudo apt-get install build-essential
sudo apt-get install libtiff4-dev libjpeg8-dev zlib1g-dev \
libfreetype6-dev liblcms2-dev libwebp-dev tcl8.5-dev tk8.5-dev python-tk \
python3-dev python3-setuptoolsi
```

### Fedora
```
sudo yum groupinstall "Development Tools" "Development Libraries"
sudo yum install libtiff-devel libjpeg-devel libzip-devel freetype-devel \
lcms2-devel libwebp-devel tcl-devel tk-devel
```
    
### Installing Python Libraries
```
sudo pip install virtualenv
git clone https://github.com/WWUDevOps/website.git
virtualenv website
cd website
```

Enter the virtual environment.
```
source bin/activate
```

Install the requirements.
```
pip install -r requirements.txt
```

## Building

Output lives in `build/` and the stuff you want to edit is in `source/`. Images
and things go in `source/static/`.

Slides will go to `build/slides`.
```
make slides
```

To preview roughly how it'll look on
[wwudevops.github.io/website][WWU DevOps Website].
```
make html
```

Leave the virtual environment.
```
deactivate
```

<!-- Links -->
[WWU DevOps Website]: https://wwudevops.github.io/website
[WWU DevOps Slides]: https://wwudevops.github.io/slides
[OSU DevOps BootCamp]: http://devopsbootcamp.osuosl.org/en/latest/
