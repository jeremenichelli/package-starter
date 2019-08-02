# package-starter

🚀 Template repository for package maintenance and publishing.

## Motivation

As I got tired of creating the same file structure for quick library scaffolding and package publishing, I decided to do a repository tempalte I (and you) can use every time  I start a new project.

It's important to note that the workflows are highly opinionated around my preferences when pushing minimal and not-complex packages to the ecosystem, this means it might not feed or adapt to your needs, but feel free to start a discussion in the issues inc ase there are things you would like to see or improve.

## How the base project works

This template is relying on other great open source projects to achieve normal project cycles.

 - For publishing it uses microbundle by Jason Miller, it provides transpiling, minification and source map generation.
 - For test it uses ava, which will detect any `.test` or `.spec` file in the project.
 - Using husky for git hooks, this template will run prettier to format files and run tests before every commit.
 - It will also check the format of your commit messages using conventional-commit, this is an important part because it will automate package publishing using continuous integration.
 - Finally, using Travis and semantic release it will generate a new version of the project on every push to master.

_Read more about how to ensure this works correctly in the Initial Setup section._

## Initial Setup

To make sure the automatic publishing works correctly follow these initial steps:

 - In GitHub press the **Use this template** button on the repository page.
 - Clone the repository on your local machine and run `yarn` to install dependencies.
 - In the `package.json` file replace `package-starter` with your project name and the rest of the information like description, author, repository, etc.
 - Commit the changes, run `npm publish`, tag the release with `git tag "v0.0.0"` and then `git push origin master --tags`, this is important since semantic release relies on tags to know what's the next version to publish.
 - Go to Travis, add your project and configure an `NPM_TOKEN` and a `GITHUB_TOKEN` to allow package publishing on every push to master.

Now, let conventional commit messages and semantic release to handle all the publishing for you!

_Happy coding!_

## LICENSE

By the default the template includes a MIT License, feel free to change it for the one that suits better the legal needs of your project.
