# CoughSyrup
# An Effort to Ease Board Creation and Editing in CoughDrop

## Overview and Access Information

We are doing our development within a fork from the CoughDrop/coughdrop repository itself.
See our development here: https://github.com/uwcse481h-2017/coughdrop

## Current Abbreviated Plan as of 2/8/17
######(copied from Assignment 3)

###Project Goals and Scope:
Our project will focus on significantly reducing the time needed to create boards, and also to edit them. We will be adding four main features to achieve these two goals:
  1. A way to set user-wide defaults for board layout, button color, text size, etc.
  2. An automatic board creation function to suggest a board based on the topic you would like to talk about, and allow you to edit it.
  3. Import board through csv file
  4. A more streamlined editing UI to both edit the suggested boards and existing boards the user has in his/her account.
We decided to remove the goal about improving “part of speech“ auto classification and encouraging grammatical sentence selection by the user. We realized after talking with the CoughDrop developers that CoughDrop already automatically classifies words as nouns, verbs, etc. We will just be working to make this a more visible and known feature. We believe this is possible by adding button color defaults for parts of speech in the user preferences wizard, and clearly showing the user that this is a setting that exists.
We also decided for now not to add integration with Google Images due to possible copyright issues. We plan on using the existing API within CoughDrop, which can search multiple creative commons sources including OpenSymbols, Flickr, Public Domain Images, and Pixabay. However this may change after conferring with our Needs Expert.

Since we have decided to build within the CoughDrop code, all board creation, hiding, or deletion will be handled through the user’s account, not a separate application built on top of it. Therefore, login and permissions will all be handled through existing CoughDrop code. Only those with the login for the account or existing permissions to edit the boards (i.e. for speech language pathologists or teachers) would be able to make edits or import boards. If these people give their devices to others to use (like if they want to allow a friend to create a board, for example), this could be possible, but the teacher or care team member would need to login first. Therefore whether care team providers can create, hide, or delete boards will all be handled through existing CoughDrop functionality.
We do understand that our work assumes an internet connection for creating and editing boards. We believe CoughDrop currently requires this. Although it would be possible to edit the code base to allow creation of boards offline that then would sync once wifi is acquired, we believe this would be very difficult with an existing code base, and will not be possible in our current time restrictions and the scope of our project.
In terms of what would happen if the system crashes mid board creation, we will fall back to how CoughDrop already handles this case. There is currently a save button in the create/edit interface. Anything the user has manually saved will be saved, otherwise anything else unsaved when the system crashes is lost. Our work will not add any new functionality changing this behavior.

### Technical Overview
Development for our project will occur within the CoughDrop code base. The existing CoughDrop code has a Rails backend and an EmberJS frontend. We are currently still working on spinning up our dev environment, but we will encompass it in a Docker image, which we will share between our three machines from development from this point on. The technical dependencies for the stack setup portion are:
* Ruby on Rails (bundler, foreman)
* Postgresql
* Redis
* EmberJS (bower, watchman)
* Docker
* And languages Ruby, JavaScript, HTML, CSS, (and possibly a separate Python backend for machine learning tasks)
