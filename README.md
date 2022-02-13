# Angular Tutorial <!-- omit in toc -->

This is based on the [Getting started with Angular](https://angular.io/start) guide.

- [Setup](#setup)
  - [Cloning the project in GitKraken](#cloning-the-project-in-gitkraken)
  - [Open the project in VS Code](#open-the-project-in-vs-code)
- [Running your project](#running-your-project)
- [Setting up GitHub Pages](#setting-up-github-pages)
- [Follow along with the tutorial](#follow-along-with-the-tutorial)
- [Run `ng lint`](#run-ng-lint)

## Setup

### Cloning the project in GitKraken

1. First, Open [GitKraken](https://www.gitkraken.com/git-client). If you already have a project open, close it or open a new tab.
2. Click "Clone a repo", select "GitHub.com" and find this repo in "Repository to Clone"
3. Select where to put it and clone it
4. You can then click "Open Repo" from the notification that appears to open the repo

### Open the project in VS Code

Launch Visual Studio Code, and then choose `File -> Open Folder…`. Navigate to your clone
of the repo and choose `Open`.

You may see a dialog that looks like this if you don't already have the recommended extensions:

![Dialog suggesting installation of recommended extensions](https://user-images.githubusercontent.com/1300395/72710961-bf767500-3b2d-11ea-8ea4-fbbd39c78da5.png)

Don't worry if you don't get the dialog, it is probably because you already have them all installed.

Like in previous labs, click "Install All" to automatically install them.

## Running your project

The first time you run your Angular project, you will need to run `npm install` so that all the dependencies managed by npm will be installed. Once you have successfully run `npm install`, in order to serve up the project, you will type
**`ng serve`**. This will trigger the various tools in the
client side portion of the project to build and host your client side
application on their own little web-server, available by default at [`localhost:4200`](http://localhost:4200/). If the development server is running, you will be able to see the application (a simple "phone store").

When you open it in the browser you should be greeted with something that looks like this:

![image](https://user-images.githubusercontent.com/1300395/105233127-07f4b400-5b2f-11eb-9c6f-3f51594f684e.png)

## Setting up GitHub Pages

We have setup a GitHub Actions workflow to automatically build and deploy whatever is on the `main` branch to GitHub Pages (using the `gh-pages` branch to store the built version). The part you need to do is enable GitHub pages on this repo just like in Lab 1.

On GitHub, you'll need to visit the *settings* for your repository and change
the *GitHub Pages* settings. Under the "Pages" section, you'll need to select
the branch `gh-pages`, leave everything else at their defaults, and save your settings.

![Pages settings for the repository](https://user-images.githubusercontent.com/302297/152859858-cbf248c6-5beb-439c-ad3d-f962c091dca8.png)

> When you publish your site to GitHub pages, GitHub will display the URL
> where you can find your published site. The primary repo we use to manage
> this lab is published
> at <https://umm-csci-3601.github.io/angular-tutorial/>;
> yours will be at a different URL but should look somewhat similar.
>
> :bangbang: Once you have that URL, please include it in the "Website" box in the
> description at the top of your GitHub project page. Click the "Edit" gearbox button by "About" on the
> right hand side (just under "Settings") and that should give you a "Description" and
> a "Website" box; paste the URL into the "Website" box. That will make it a lot easier
> for us to go through all the projects and see your work.

![Edit button for "About" section for the repository](https://user-images.githubusercontent.com/302297/152860484-2776c873-f80c-4a82-bc50-e136c8563626.png)

---

## Follow along with the tutorial

**Make sure you commit regularly as you go through the
tutorial, making sure to provide descriptive commit messages.
You should probably make a commit after each new feature
is completed or concept is processed.**

Now your job now is to go through [the "Getting started with Angular" tutorial](https://angular.io/start), up to (but not including) the last section ("Deploying an application"). You can skip the initial "Create the sample project" section and instead clone this repo and open it in VS Code and run it as described above. You will start with ["Create the product list"](https://angular.io/start#create-the-product-list).

> Feel free to read that last section on deployment, but our
> deployment mechanism in this class will be totally different than
> what they describe there.

To "do the lab", you will essentially follow along and do whatever it
says to do in the tutorial. This is mostly adding or modifying content
in various files that will already exist in this repository.

There are, however, times, when you need to create a new *component* or
*service* (terms explained in the tutorial). In the tutorial you do this
through a StackBlitz menu, which won't exist for you. You will instead
use `ng generate` in the terminal.

For example, roughly in the middle of the first section of the tutorial,
you encounter this:

![StackBlitz generate component menu](https://user-images.githubusercontent.com/1300395/106520616-aaebed00-64a2-11eb-8a51-a11907bd486e.png)

We will instead generate this new component in the terminal using:

```bash
ng generate component product-alerts
```

**You must be at the top level of your project in the terminal window
when you enter an `ng generate` command.**

This will do the same thing that the menu would do in StackBlitz, but
via the terminal instead. After you do that you should check that you
indeed get the same new files that the tutorial says that you should.

There will be various other times in the tutorials where they tell you
to generate either a *component* or a *service*. You should always do
that through either `ng generate component ...` or
`ng generate service ...` as appropriate (with the name of the component
or service in place of the `...`s above). (Note that the tutorial
*always* tells you the name of the component or service that you are
creating. Make sure you use the correct name or subsequent steps will
likely not work.)

[`ng generate`](https://angular.io/cli/generate) is a powerful tool that's worth getting to know. It
"understands" the structure of Angular apps and file structures, and can
create the collection of related files needed for a new component
or service, or any of a number of other Angular tools. When it creates
something for you, it creates all the necessary files with the correct
names and in the correct places. It also
helps make sure that these new things are correctly "wired in" so they
get compiled and loaded when you run your app.

## Run `ng lint`

We've added support to this repository for ESLint, a tool that provides
some basic code quality checks. Since you're doing this lab on your own,
we haven't set up automated checks that block you from pushing icky things to `main`, but that doesn't mean you shouldn't
keep an eye on the quality of your code. You should probably run
`ng lint` (in the terminal at the top level of the repo) every now and
then to make sure that you're not introducing "uglies" along the way.

> GitHub Actions will perform an `ng lint` check each time you commit,
> so you probably should run `ng lint` before each commit as a way of
> trying to keep your public-facing repo nice and shiny.

*Absolutely* ask questions if `ng lint` complains about something
and you don't really understand what it's talking about.
