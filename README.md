# Updating docs!!!!!!!!!!!!

To update the documentation:

1. Setup. Fork and clone the repository
- Fork the `johnx25bd/os-data-hub-documentation` repository onto your own Github account. 
- Open VSCode to the folder where you want to repository to live.
- Clone _your_ fork of the repo onto your local machine by opening the VSCode Terminal (View > Integrated Terminal) and running

```console
git clone git@github.com:<your github username>/os-data-hub-documentation.git
cd os-data-hub-documentation
```

Your computer will copy the remote repository onto your local computer. 

2. Familiarize yourself with the repo
- Open the folder int heh VSCode file explorer (upper left)
- Navigate to the `/docs` folder - here is where all of our documentation Markdown will live.
- Click on a `.md` file to view in the VSCode editor.

3. Edit some docs
- Open the document you want to edit. 
- Write Markdown documentation as you please. You can view the rendered markdown with the "Open Preview to the Side" button upper right (side by side icon with magnifying glass)

4. Add an image
- In the docs folder you're working in, create or find the `./assets` directory
- Drop the image file into that folder in VSCode or in Finder (AKA File Explorer)
- Write a Markdown tag for the image and include the relative path to the file, including filename and extension

```markdown
![alt text here](./path/to/file.png)
```

The image should show up in your preview to the right - if it's a broken image icon examine your link. Also, you can put URLs in the link field!!

5. Commit and push the changes
- In the Terminal, check that everything looks good by running `git status`. You should see the files / directories you've modified or added noted
- If it all looks good, run `git add` 
- and then `git commit -m "A message describing the contents of the commit"`
- Run `git push origin main` to push to your remote repo - the fork you created earlier. 
- You'll now see the changes reflected on github.com - check to make sure. 

6. Create a pull request
- Go onto your repository page on github.com. There should be a bar that says "This branch is x commits behind johnx25bd:main" or something like that
- Click the Pull request button to the right of that bar
- Make sure the base repository is johnx25bd/os-data-hub-documentation, and the head repository is your fork
- Examine the differences to make sure they are *only* the changes you made
- Create pull request. This will notify me that you want to merge changes in and that you've checked to make sure it all looks good - links are working - images work etc.
- I'll accept and your changes will now be reflected on the main repo.



# Website

This website is built using [Docusaurus 2](https://v2.docusaurus.io/), a modern static website generator.

## Installation

```console
yarn install
```

## Local Development

```console
yarn start
```

This command starts a local development server and open up a browser window. Most changes are reflected live without having to restart the server.

## Build

```console
yarn build
```

This command generates static content into the `build` directory and can be served using any static contents hosting service.

## Deployment

```console
GIT_USER=<Your GitHub username> USE_SSH=true yarn deploy
```

If you are using GitHub pages for hosting, this command is a convenient way to build the website and push to the `gh-pages` branch.
