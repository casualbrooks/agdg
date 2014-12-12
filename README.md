agdg
====

(How to dev located near the bottom)

albuquerque game dev guild

We are building a website:
(Instead of a grandiose crazy thing, a thing we can digest, that may later grow)

All it needs to have...

### add a AGDG member profile, a member has:
- a name
- a short description
- a photo (or maybe some sort of avatar)
- a website
- games they are part of
- "classes" (artist, dev, music, video, marketing, etc.)  

### add a game, a game has:
- a name
- a short description
- a screenshot (of a particular size)
- a website
- a video (optional)
- links to members
- progress through achievements
- progress bar

### add Achievements:
- art, concept
- art, completed
- concept, narrative
- concept, mechanics
- concept, prototype
- game, alpha done
- game, beta done
- game, playable
- game, balance
- marketing, website
- marketing, video
- music/sound effects

### other Ideas:

#### avatar generation
- retro/pixel style
- custom faces / hair / clothing accessories
- avatar's have classes
- avatar's have levels, experience (the more games someone works in, the more achievements they get)

#### fake money
- people (in guild and outside of guild) get coins/gems/things
- they can assign to game projects as a form of voting for the things they want to see completed
- possibly game devs can also put up polls that people can then vote with their fake money things in to help direct the game development (vote for levels, character classes in games, additional content packs,...)

## How to do dev stuff on your own machine
So, you want to contribute to development?  Right on.  To get started, check
out the wagtail docs on how to install wagtail on your box.

http://docs.wagtail.io/en/latest/getting_started/installation.html

Heads up, you'll want to install all this stuff on a virtual machine or a
vagrant box, ideally one running Ubuntu 14.04 if you want something to similar
to the production environment

Once you've got everything set up, just cd into the project root and clone
this repo.  Once you're in, go into `settings/base.py` and look for the
following bit of code...

    # Application definition

    INSTALLED_APPS = (
      'django.contrib.admin',
      'django.contrib.auth',
      'django.contrib.contenttypes',
      'django.contrib.sessions',
      'django.contrib.messages',
      'django.contrib.staticfiles',

      'compressor',
      'taggit',
      'modelcluster',

      'wagtail.wagtailcore',
      'wagtail.wagtailadmin',
      'wagtail.wagtaildocs',
      'wagtail.wagtailsnippets',
      'wagtail.wagtailusers',
      'wagtail.wagtailsites',
      'wagtail.wagtailimages',
      'wagtail.wagtailembeds',
      'wagtail.wagtailsearch',
      'wagtail.wagtailredirects',
      'wagtail.wagtailforms',

      'core',
    )

You'll want to change `core` to `agdg` in the bottom of the `INSTALLED_APPS`
tuple

You're almost there.  Now cd into your project root and type
`python manage.py migrate` to get everything set up

To see if everything works, go ahead and run `python manage.py runserver` and
visit the site in your browser.  If you don't see any error messages, then
congrats
