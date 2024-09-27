# How to: Raspberry Pi

Welcome to the *Introduction to Raspberry Pi* repository by the [Hedron Hackerspace](https://hhacker.space) over in Portland, Oregon. This repository contains instructional slides and activities that are supplementary to a class held at the hackerspace to teach you how to use Linux, make your own Python applications, use the GPIO pins, and much, much more. While you can use these modules to learn on your own, I highly recommend you stop by the space to get help if you run into issues. Or if you can't join any of the in-person sessions, you can join our Discord server and ask for help there (though if it's a hardware issue, it may be a bit more difficult).

**THIS REPO IS A WORK IN PROGRESS AND THINGS ARE SUBJECT TO CHANGE!!**

# Why did you make this?

This was primarily designed to be run as an in-person or remote class, which is why some of the information on the slides is a little limited. It was more of a reminder for myself to remember what to cover and what to elaborate more on. If it were any more verbose, you might as well read the documentation or check support threads on the Raspberry Pi forums (or heaven forbid Stack Overflow). Having someone work along side you:

* Makes it much more engaging
* Makes it easier for the material to actually stick
* Allows for going in-depth in certain topics
* Feel safer about doing certain things or running certain commands (like using the Terminal)

Even if you decide not to take the in-person or remote classes, you should still be able to get something out of these slides like a new reference point for troubleshooting or terminal commands.

# What can I expect to learn?

Currently, there is only the getting started steps in setting up the Pi hardware, updating everything, and basic terminal usage. However, there are lots of modules that I plan on creating.

Fully complete modules:
- [x] 0. Raspberry Pi Introduction
- [x] 1. Basic Setup
- [ ] 2. Introduction to Python
  - [ ] 2a. Variables, Math, Control Flow, and Functions
  - [ ] 2b. Lists/Dicts, Files, Modules/Libraries, and OOP (objects)
  - [ ] 2c. Using GPIO with Python
- [ ] 3. Using git and GitHub
- [ ] 4. Self-hosting with Docker
- [ ] 5. More TBD...

# How are the slides rendered?

I am using a VS Code extension called Marp which turns markdown into a slideshow presentation. Since it's all just markdown, it was really easy to just get started and learning some of the new stuff like working with images was not bad at all. There are some caveats to using Marp like using 2 columns on one slide isn't intuitive at all (have to use custom HTML and CSS, I am not a web dev), image options, and a lot of other QOL things. But with all its faults, it's much better than using some proprietary software that requires online access to use. I will probably be using the RISE plugin for Jupyter Notebooks when I make the AI/ML slides (for obvious reasons), but for pretty much everything else, this is a great extension that I highly recommend if you want a simplistic slideshow designer.

# Where can I get help/suggest a change?

Please raise an issue following the template as closely as possible. This makes it much easier to fix any issues you come across.

If you are suggesting a change, please know that you are just giving a suggestion. Your suggestion may or may not be implemented based on what you are suggesting. Again, follow the template as much as possible, and your chances of the change going through will be much higher.