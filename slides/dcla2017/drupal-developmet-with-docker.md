---
title: Drupal Development with Docker
verticalSeparator: <!--v-->
theme: serif
revealOptions:
    transition: 'fade'
---

<!-- .slide: data-background="./images/drupalcampla-presentation-template-1024x768.png" -->
## Drupal Development with Docker

Casey Grzecka
### UCLA Library

---

<!-- .slide: data-background="./images/drupalcampla-presentation-template-1024x768.png" -->
# Docker
<img data-src="./images/docker.png">
Note:
* Basic background
* good for deployment

<!--v-->
<!-- .slide: data-background="./images/drupalcampla-presentation-template-1024x768.png" -->
## Why local Docker
* VM vs container
* better resource utilization
* dependency isolation
* separation on concerns

Note: speaker notes FTW!

---

<!-- .slide: data-background="./images/drupalcampla-presentation-template-1024x768.png" -->
What does it take? My experience rolling my own. 
* Why?
    * my vagrant local Host via virtualbox mount sucked and was sooooo slow
    * mimic arch that we will be doploing to
    * multiple projects with diff deps
    * docker was so new and shiny
    * I don't like (manually configuring) VMs
    * docker native in linux
* Don't treat it like a VM
    * unless you want to, I'm not your mom
        * do what you want
        * that's how I started
    * docker run -it ubuntu bash
        * and you are off
        * apt get install vim Foo
        * but you won't get far before you just did the old way, the new way
        * you need ports open, services started, volumes mounted, etc.
    * so, let's just re-run with new configs, wrong, can't data does not persist without volume mounted, host or otherwise
        * you could docker export, but dont
    * so, build the repetitive tasks into a Dockerfile...
        * so easy, basically bash
        * and make each image inherit only what it needs...
        * show z3cka/c9 + php + drupal 
        * where do we install and run MySQL?

---

Can we start coding drupal awesomeness yet? No! More local arch to manage!

Separate concerns
* Put services in different containers
* don't have to over do it
    * don't have to worry about making it one process, you will go mad
* do the next iteration of clown computing just with containers
* use docker-compose
    * yaml that sets up all your services
    * it's awesome, but wouldn't it be nice if you didnt have to start from scratch?
        * everything in the lamp stack has been dockerized to the teeth!
        * xkcd VM til fired comic
        * use a tool
        * what if I told you this tool would manage your VM too!?

Introducing Docksal
* Dock---s------al 
* Docker s Drupal
    * maybe the s is from the s in dorsal, as in the dorsal fin of the Docker whale. 
        —S. Gurnick
* Say generally what it does

Docksal VM management
* docker still needs a VM to run on OS X* le sigh
* Commands
    * create
    * resize ram

Docksal Project handling
* pl — project list
* project create demo
* existing project

Docksal envronment
* Env file
    * set docroot
    * enable xdebug

Docksal yaml
* Define services via docker-compose with images, etc.
* php version image
* add solr demo

Docksal cli: fin
* fin db demo

Docksal share!!!

Try anything! (Almost)
* Git gogs server + droneCI
* get crazy with rancher