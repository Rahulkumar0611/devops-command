prod to master branc
git checkout master
git reset --hard prod
git push origin master --force
 
 
============================
master local ->  master branch -> master branc code merge to  prod branch ->  in server pull prod code -> docker compose down -> docker compose build ->  docker compose up -d
 
 
step 1:- (in local system ) 
switch to master branch (git checkout master)
 
step 2:- 
git add .
git commit -m "commit message"
git push origin master
 
step 3:- (merge master code to prod branch)
git checkout master
git pull origin master
 
git checkout prod
 
git pull origin prod
 
git merge master
 
git add .
git commit -m "Merge master into prod"
 
git push origin prod
 
step 4:- (In server)
git pull origin prod
 
docker compose down
 
docker compose build
 
docker compose up -d
 
 
 
=================================
 
to check docker container logs
docker log container_id
 
 