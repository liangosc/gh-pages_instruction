# How to view your html output using gh-pages branch in your github

I am sure there are many ways to do it, but this is how I did it.

## Preparation
1, make a repo if you haven't;

2, go to your local directory, and clone the repo you just made, using the following command:
```
git init
git clone http://github.com/yourUserName/reponame.git
```

3, put your files (ipynb, Rmd... don't forget the html file you generated) to your local directory, and add/commit/push them to your GitHub repo:
```
git add -A
git commit -m 'your message here'
git push
```

## Make a gh-pages branch
(for this section, I am assuming your files are arealy pushed to your GitHub repo)

0, in your command line window, go to your local git repo directory.

1, create the gh-pages branch by using:
```
git checkout -b gh-pages
```
This tells GitHub to make a new branch which is identical to your current branch (which I'll assume it's the master). then push it to GitHub:
```
git push origin gh-pages
```
Well, that's it. If you have a .html file called myresult.html under your repo "reponame", you should be able to view it here: http://yourUserName.github.io/reponame/myresult.html

2, switch back to master if you want to continue working:
```
git checkout master
```
**I would suggest that always working under your master branch.**

3, you can view your current branch by:
```
git branch -v
```

## Update the gh-pages branch
1, Now you have made some changes to your ipynb or Rmd file, and generated a new myresult.html. Let's commit the changes:
```
git add myresult.ipynb myresult.html
git commit -m "MESSAGE"
```

2, swich to gp-pages branch:
```
git checkout gh-pages
```
(note that you don't need to type a '-b' here)

3, pull your changes from master branch into gp-pages:
```
git pull . master
```
4, now switch back to master branch:
```
git checkout master
```
5, push both branches to your GitHub:
```
git push origin master
git push origin gh-pages
```
Now you should be able to see the updated html page. If not, wait for a few minutes.
