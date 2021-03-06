# svn-utils
Small utilities for working with Subversion

#### svn-lookback.sh
Find an SVN revision that occurred N revisions ago.
```bash
# Syntax
./svn-lookback.sh -u <SVN url> -l <limit>

# Example: Find 500 revisions ago from HEAD

./svn-lookback.sh -u https://svn/proj/trunk -l 500

# Example: Find 4 revisions before 9871

./svn-lookback.sh -u https://svn/proj/trunk@9871 -l 4
```

#### git-svn-cloneback.sh
Perform a `git svn clone` based on the last N revisions of the SVN repo.  This is useful if you have a giant SVN repo you want to move to git, but you don't want to clone the entire history.
```bash    
# Syntax
./git-svn-cloneback.sh -u <SVN url> -l <limit>

# Example: Clone only the last 500 revisions from the latest SVN revision

./git-svn-cloneback.sh -u https://svn/proj/trunk -l 500

# Example: Clone starting from 4 revisions before SVN r9871

./git-svn-cloneback.sh -u https://svn/proj/trunk@9871 -l 4

# Example: Clone last 20 revisions into mydir and pass some parameters to the clone

./git-svn-cloneback.sh -u https://svn/proj/trunk -l 20 -o mydir --authors-file=svn-auth.txt
```
