# similarity_checker
&copy; Jeremy Ellman 28/02/2022   Published under the <a href="https://github.com/eb0x/similarity_checker/blob/main/LICENSE">MIT license</a>.

A Jupyter notebook to find collusion in student submitted Jupyter notebooks. A cheating detector. 

Collusion is when students who should be working individually work together and submit identical (or visually identical) work. Collusion is easy to spot when two source files are seen side by side, but is often missed when large classes have multiple markers, or take days to mark.
This is an issue with Jupyter Notebooks as Python source code can be mixed with Markdown free text that disguises the collusion.

The notebook uses Jupyter to convert the source files to Python with Markdown as comments. Comments are then stripped, and each file represented as tf/idf vector. A cosine similarity matrix is then found for the cohort using scikit-learn. The similarity score ranges from 0-1.0, where a score of 1 is completely identical.

All file groups that exceed some similarity theshold (initially 0.8) are then identified and written to a summary csv file (or reported inline).

Students working with given examples, or on the same problem will often have code in common (e.g. database connection strings). Consequently the instructor needs to determine whether academic misconduct (cheating) really took place. The similarity checker just guides you where to look.

The similarity checker processes ~140 files in ~20s on a modest PC.
