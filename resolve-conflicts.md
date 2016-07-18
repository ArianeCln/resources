**How to resolve conflicts**

1. git co dev
2. git pull origin dev
3. git co your-branch
4. git merge dev
5. ... resolve your conflicts ...
6. git add .
7. git commit -m "resolving conflicts"
...


**TIP**

if conflicts in db structure --> just run *rake db:migrate* ; it will rewrite the file
