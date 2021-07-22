![docker pulls](https://img.shields.io/docker/pulls/jupyter/r-notebook.svg) ![docker stars](https://img.shields.io/docker/stars/jupyter/r-notebook.svg) [![](https://images.microbadger.com/badges/image/jupyter/r-notebook.svg)](https://microbadger.com/images/jupyter/r-notebook "jupyter/r-notebook image metadata")

# Jupyter Notebook R Stack

* [Jupyter Docker Stacks on ReadTheDocs](http://jupyter-docker-stacks.readthedocs.io/en/latest/index.html)
* [Selecting an Image :: Core Stacks :: jupyter/r-notebook](http://jupyter-docker-stacks.readthedocs.io/en/latest/using/selecting.html#jupyter-r-notebook)


When using the `r-dsci-100` Docker image with JupyterHub and DockerSpawner, 
be sure to set `c.DockerSpawner.post_start_cmd = 'sh -c "cp -a /tmp/user-settings/. /home/jupyter/.jupyter/lab/user-settings"'` 
in `/srv/jupyterhub/jupyterhub_config.py`.
