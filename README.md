# eQTLpipeline

## Installation

You will need the latest version of devtools. First install the release version:

```R
install.packages("devtools")
```

then update it to the latest developement version:

```R
devtools::install_github("devtools")
```

Finally you can install the latest development version of tRap from github with:

```R
devtools::install_github("matthiasheinig/eQTLpipeline")
```

## Developing

### git

We use the fork & pull model for developement (based on a README from the Shogun project)

Visit the eQTLpipeline github page and click on the Fork button. Then clone your copy of the repo and add the original eQTLpipeline repository as upstream:

```
git clone git@github.com:<your id>/eQTLpipeline.git
git remote add upstream git@github.com:matthiasheinig/eQTLpipeline.git
git checkout --track origin/master
```

Now you're ready to work on your feature. First create a branch:

```
git checkout -b new_feature_name
```

and now you can develop your code and commit to this branch.

Once the feature is done, rebase your branch against the current upstream master:

```
git fetch upstream
git checkout master
git rebase upstream/master
git checkout new_feature_name
git rebase master
```

And now you can push into your repository:

```
git push
```

Now go to the github website and do a pull request.

### R development

After creating a branch in your local git repository, modify the R or C++ code however you need and then run R from inside the root of the package's directory (e.g. eQTLpipeline/) and run a few devtools commands:

```R
library(devtools)
load_all() # this should recompile the C++ code
check()    # does some/all of the above, as well as running R CMD check
```

There are a few other useful devtools commands:

```R
install()  # install the package in your R library directory
document() # just rebuilds the documentation
test()     # just runs all tests
build()    # build a binary package
```

For more information check out the devtools site.