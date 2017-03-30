The question of supporting Bootstrap 4 and / or Bootstrap 3 as part of this project comes up very often. The aim of this article is to present rationales and thinking that made ng-bootstrap to support Bootstrap 4 only (at least at the moment).

### Bootstrap 3 is no longer maintained

If you follow what is going on in the [Bootstrap repository](https://github.com/twbs/bootstrap) you will notice that Bootstrap 3 issues are being closed without fix as Bootstrap 3 is no longer maintained. This means that when you discover a bug in Bootstrap 3 or want to add even the slightest feature you are out of luck... All the action is happening on Bootstrap 4 front and this is the only version that will be maintained in the longer run.

### Supporting 2 versions of Bootstrap technically difficult

But why not supporting Bootstrap 3 _and_ Bootstrap 4 at the same time, you might ask. It is a valid question and one we've tried to find a technical answer to on several occasions. It turns out that with the current version of Angular there is no easy way to have different versions of templates for the same component (if you can see a clean technical solution please open an issue to discuss). 

### Supporting 2 versions of Bootstrap would drain resources that can be used to make awesome widgets

Supporting 2 versions of the CSS framework is not an easy task. Essentially we would have to find a way to have different templates per component, generate different documentation and demo pages, release 2 different versions of the library and adjust the build to support all this. This can be done but we've decided that the time spent on adding support for the unmaintained CSS framework version could be better spend on making World-class widgets that support just Bootstrap 4. There are tons of things that need attention (accessibility, animations, customizations etc.) and we've prioritised those over Bootstrap 3 support.

### But I can't use Bootstrap 4 as it is still in alpha

We are painfully aware that some organisations will freak out when they see `alpha` in any library version. The good news is that Bootstrap 4 is close to releasing its beta and we will release beta of ng-bootstrap as soon as Bootstrap 4 bumps up its version. We believe that in few weeks this "problem" will naturally go away.   

If you are starting a new project the choice should be no-brainer - it will be much, much easier to migrate from Bootstrap 4 alpha to Bootstrap 4 final as compared to doing Bootstrap 3 -> Bootstrap 4 migration.

### But I've got my project that runs on Bootstrap 3

First of all you can't stay on Bootstrap 3 forever as you would be running on an unmaintained version. So why not starting migration effort now? 

If you still believe that you absolutely need to support Bootstrap 3 you can always step in and add Bootstrap 3 support to this project. This is open-source effort and we would welcome all contributions, provided that you are willing to contribute Bootstrap 3 version and maintain it on the long run.

If you want to step in or discuss Bootstrap 3 support please open an issue to discuss. 