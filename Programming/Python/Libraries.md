
### Install packages

To install packages, use `pip`. It is a command-line tool that allows you to install and manage Python packages.

Here are some useful commands :

  ```bash
  # install a package
  pip install package_name
  # install a specific version of a package
  pip install package_name==version_number
  # upgrade a package
  pip install --upgrade package_name
  # uninstall a package
  pip uninstall package_name
  # list all the installed packages
  pip list
  # show informations about a package
  pip show package_name
  ```


### Graphviz

Create an image out of a graphviz graph

```shell
dot -Tpng graph.dot > output.png
```