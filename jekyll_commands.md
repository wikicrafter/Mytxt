jekyll new example 

cd example 

bundle exec jekyll server 

jem install bundle / it must be installed 

if ther is a error: bundle add webrick 

jekyll server 
---------------
when changing theme shut down server rhen run: bundle install
but before that we gonna specify theme name on root folder in gemifile
 
then after that update _config.yml

then one more time shutdown server and run: bundle exec jekyll server 

___
for publishing it on github we write on _config.yml baseurl:"the repository name in which we upload it"
if you buy custom domain then write ther you domain name
---
git init

git checkout -b gh-pages

git status

git add .


git commit -m "initial commit"

git remote add origin "repository link"

git push origin gh-pages

