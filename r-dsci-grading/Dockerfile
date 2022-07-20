# Copyright (c) UBC-DSCI Development Team.
# Distributed under the terms of the Modified BSD License.
ARG BASE_CONTAINER=ubcdsci/r-dsci-100:latest
FROM $BASE_CONTAINER

LABEL maintainer="Tiffany Timbers <tiffany.timbers@stat.ubc.ca>"

# switch to root for installation
#USER root

RUN mamba install --quiet --yes "rise"

# install nbgrader and rise extension
RUN mamba install --quiet --yes "nbgrader=0.7.1" \
    && jupyter nbextension install --sys-prefix --py nbgrader --overwrite \
    && jupyter nbextension enable --sys-prefix --py nbgrader \
    && jupyter serverextension enable --sys-prefix --py nbgrader 

RUN mamba clean --all -f -y 

# downgrade nbgrader to 5.6.1 so that feedback forms can be generated
#RUN pip install "nbconvert<6"

# downgrade jupyter-client to 6.1.12 / nbclient to 0.5.3 to avoid errors with coroutines
#RUN pip install nbclient==0.5.3
#RUN pip install jupyter-client==6.1.12

# switch user
#USER $NB_UID
