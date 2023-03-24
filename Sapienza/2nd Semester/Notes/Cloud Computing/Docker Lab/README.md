# Converting to PDF
To convert the [submission](submission) markdown file into `.pdf`, do the following steps:

1. Install [pandoc](https://pandoc.org/installing.html)
2. Run
   ```bash
   pandoc submissino.md -f markdown -t pdf -s -o submission.pdf
```