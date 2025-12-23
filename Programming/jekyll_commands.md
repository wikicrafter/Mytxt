jekyll new example 
---
cd example 

bundle exec jekyll server 

jem install bundler / it must be installed 

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

---

## 🚀 Keep This Project Going

Creating comprehensive guides like this takes time, research, and lots of coffee! ☕

**Here's how you can help:**

🌟 **Star this repository** - It's free and helps others find these guides  
💝 **[Support on Ko-fi](https://ko-fi.com/gigaa)** - Buy me a coffee (or energy drink!) to fuel more content  
👤 **Follow on GitHub** - Be the first to know about new guides and updates  

*Every star, every coffee, every follow makes a difference. Thank you for your support!* 🙏✨

