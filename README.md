# Learning
## upgrade pip under anaconda
1. Install anaconda under C:\
2. find the path for anaconda, go to command prompt, cd "path for anaconda", type in "python.exe -m pip install --upgrade pip"
3. Restart Jupyter, using the Jupyter app.
## install R in jupyter
1. Open anaconda prompt
2. Type in "conda install -c r r-essnetials"
### install new R packages when using Jupyter notebook:
1. install under R studio, b/c it is difficult to install using Jupyter
### Using a new windows version of R in Jupyter notebooks
https://stackoverflow.com/questions/51647561/using-a-new-windows-version-of-r-in-jupyter-notebooks:
Note the differences in the version.string and nickname variables in particular.

Now in your Jupyter notebook type:

R.home()

Which will give the output like:

"C:/Anaconda3/lib/R"

The same command in RStudio or RGui will return a different path e.g.:

"C:/R/R-35~1.0"

The above values may not match those on your machine, but if they are different to each other the following steps will allow you to use the latest R instance from Jupyter.

Longer solution

Copy the above R.home() path from Rstudio (or RGui)
Open Anaconda Prompt form the start menu
Type cd /d "C:/R/R-35~1.0" where the path is the same as the one you have copied. Hit return.
Type cd bin. Hit return
Type R.exe to launch the command line R from that directory
We now need to install the package IRkernel. This package makes the version of R callable as an Jupyter kernel. Type install.packages("IRkernel") and hit return.
Type IRkernel::installspec(name = 'ir35', displayname = 'R 3.5.0') to create the latest R kernel. Note you can change the name and display name to be whatever you wish.
Exit R and close any instances of Jupyter Notebooks you have running.
Launch Jupyter Notebook again and click to create a new notebook. You should find your kernel available by its display name in the drop down box.



### unable to access index for repository http://cran.rstudio.com/src/contrib
### cannot open URL 'http://cran.rstudio.com/src/contrib/PACKAGES '

I suspect this is actually where things are going wrong (there’s “no sparklyr available” because install.packages() can’t even access the repo). Note that if you check the PACKAGES URL that it’s failing to access, there’s definitely an entry for sparklyr.

This problem is often the result of proxies, firewalls, or other traffic filtering software blocking R from accessing remote URLs, so maybe start by looking into how your system is set up on that front?

### revert R version to a previous version:
Rstudio -> Tools -> Global Options -> General -> R version -> "Change..."
