---
layout: post
title:      "CLI Data Gem Project"
date:       2019-03-04 14:26:55 -0500
permalink:  cli_data_gem_project
---


Before starting the CLI data gem project I highly suggest watching [this video](https://www.youtube.com/watch?v=_lDExWIhYKI). It is already linked in the gem project curriculum page, but watching this video gave me a mental roadmap on how to attack this project. Seeing Avi's structure gave me a foundation to build off, and made starting the project much easier. Along with that, read the **entire** page on this projects curriculum page. Before starting to code you have to make sure your idea can fulfill all those requirements. Lastly, make sure you give your gem a unique name; if your gem shares the name with another gem it will not be uploaded to rubygems.org.

I initialized the gem from the command line using `bundle gem your_gem_name`. This automates the structure-building of your gem. Tweaks will still need to be made, varying based on your gem, but watching Avi's video will help iron out some of the kinks you may face. For example, setting up my environment, load dependencies, and gem dependencies was much easier being able to reference that video. 

Once I had my environment set up and my load dependencies working it was time to get into the meat of the project. When writing your classes and methods I think it's best to just get your code to do its intended purpose before refactoring. Initially, it won't look pretty, but having working code to refactor from and reference is easier than trying to write the DRY-est code with no basis. When refactoring, you have a referral point to when your code was working that allows for more flexibility in editing.

I faced most of my problems in trying to actually publish my gem. At first, I could not publish my gem because it shared a name with another gem. To fix that you need to change `spec.name` in your gemspec file to a relevant unique name. After that I was able to publish it, but realized unless someone went into the actual directory of my code and ran the bin file there was no way of using my gem. A fair amount of googling later, I found that I had to change a couple of lines in the gemspec file. The `spec.bindir` line needed to be set equal to `"bin"` since my executable file was a bin file and not an exe file which is what it was initialized with. Then, `spec.executables` had to be changed to `spec.executables   << "nba-info"`, "nba-info" being whatever keyword(s) you want a user to input to start your gem. So I went to publish again and...failed. The last issue I ran into was with versioning. I tried to publish my gem with the same version as my previous version, and that's a big no-no. Once I updated the version, I was finally able to publish and have users download and use the gem seamlessly from their shell. 
