To convert `.md` files into `.pdf`:

1. Install [pandoc](https://pandoc.org/installing.html).
2. Run the following command, with your chosen file names.
   ```bash
   pandoc <file.md> -f markdown -t pdf -s -o <out.pdf>
```

