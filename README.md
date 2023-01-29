# myfirstrepo
Hello World Repo from scratch git usage
# ##################
# GIT PLUMBING COMMANDS

# Make a working Directory and go to the directory
	mkdir hello_world ; cd hello_world/

# Make hidden git directory and essentials git uses directory
	mkdir -p .git/objects .git/refs .git/refs/heads

# To check the tree structure of .git directory
	tree .git/

# Let check the git status
	git status

# Create HEAD file in .git directory and reference with the name of branch. So, that git will initialize the branch
	echo "ref: refs/heads/main" >> .git/HEAD

# Create any hello world text file you can direct create a hello world file.
	echo "Hello World" >> hello_text.txt

# Make a hash of a content of a file by using below command.
	cat hello_text.txt | git hash-object --stdin -w 

# To check the content by using hash value 
	git cat-file -p 557db03de997c86a4a028e1ebd3a1ceb225be238

# Now, we are updating the index of new created content of file also giving the permission in file ex - 100 represent to file and 644 represent as O=r+w, G=r, A=r .
	git update-index --add --cacheinfo 100644 557db03de997c86a4a028e1ebd3a1ceb225be238 hello_text.txt

# To check the structure of .git directory
	tree .git/

# To make write that whatever you have made a change in file and make it to stagging.
	git write-tree

# Now, we are commiting the changes using by hash value from above command
	git commit-tree 5dbf3a5ae75233e9bcb11639ec3f4e82294c751a -m "Hello File added"

# Now, we have done commit and we are going to make and inform our reference head by has value of commit.
	echo 01978293c04ca22d7bd66795b34db05d0145b2ac > .git/refs/heads/main

# Let check the git status
        git status

# To check the which branch you are currently.
	git branch

# To check the tree structure of .git directory
        tree .git/

# To check the remote of github 
	git remote -v

# To adding remote and useradd of your repo
	git remote add origin https://github.com/myrepo

# To add the origin of branch main
	git push add origin main

# To push the git of branch main
	git push -u -f origin main
