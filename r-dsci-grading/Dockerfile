# Copyright (c) UBC-DSCI Development Team.
# Distributed under the terms of the Modified BSD License.
ARG BASE_CONTAINER=ubcdsci/r-dsci-100:latest
FROM $BASE_CONTAINER

LABEL maintainer="Tiffany Timbers <tiffany.timbers@stat.ubc.ca>"

# switch to root for installation
USER root

# install Rise slide extension
RUN conda install --quiet --yes -c conda-forge rise

# install nbgrader extension
RUN pip install nbgrader==0.6.2
RUN jupyter nbextension install --sys-prefix --py nbgrader --overwrite 
RUN jupyter nbextension enable --sys-prefix --py nbgrader
RUN jupyter serverextension enable --sys-prefix --py nbgrader

# downgrade nbgrader to 5.6.1 so that feedback forms can be generated
RUN pip install "nbconvert<6"

# downgrade jupyter-client to 6.1.12 / nbclient to 0.5.3 to avoid errors with coroutines
RUN pip install nbclient==0.5.3
RUN pip install jupyter-client==6.1.12

# switch user
USER $NB_UID
