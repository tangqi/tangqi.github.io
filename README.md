# tangqi.github.io

- conda install 
  * `conda create -n web python=3.7`
  * `conda activate web`
  * `conda install -c conda-forge mkdocs=1.0.4`
  * `conda install -c conda-forge pyyaml`
  * `conda install -c conda-forge markdown==3.1.1`
  * `conda install -c conda-forge mkdocs-macros-plugin`
  * `conda install -c anaconda jinja2==3.0.3`
- newer versions may not generate correct front page (to see the installed version, use `pip show mkdocs`)
- clone this repo,
- edit or add some `.md` files (you may also need to update the `mkdocs.yml` config),
- preview locally with `mkdocs serve` 
- publish with `mkdocs gh-deploy`.
