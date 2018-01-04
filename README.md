## Ellip documentation

This is the official repository of the Ellip documentation.

This documentation is live at https://docs.terradue.com

### Getting started

Here's the procedure to install the required packages

1) Install sphinx

```bash
sudo conda install sphinx
sudo conda install sphinx_bootstrap_theme
sudo conda install sphinx_rtd_theme
sudo conda install sphinxcontrib-plantuml
```

2) If needed, set your github information:

```bash
$ git config --global user.name <github username>
$ git config --global user.email <email address>
```

### Building locally

Build the documentation by running ``make html`` or ``make latex``

#### This documentation is built with [sphinx](http://sphinx-doc.org/).