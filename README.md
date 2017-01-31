git bisect kata
===============

git bisect commands
-------------------
* `git bisect start` - start, either of below will do it so it's unnecessary
* `git bisect bad` - mark current commit bad and jump to next one
* `git bisect good` - mark current commit ok and jump
* `git bisect reset` - start over

About
-----
The latest commit in this repo is definitely broken, we can test this by running `./cat.py`. A red cat is wrong, yellow is ok. The first is definitely ok, you can jump to the first commit by

```bash
git checkout 4a37fe34508f8cae5befa620e284343f61256cdb
# or by tag
git checkout start
```

Now, using bisect find who broke the code.

The flow
--------
* clone the repo, you're on newest commit, run the test (cat.py), the cat is red so mark it bad.
* go to the first commit, run the test, the cat is ok, mark it good.
* git will jump now to some commit, run the test and mark it good or bad, until you find the answer.

The goal
--------
To find the name of the committer who made the cat red.
