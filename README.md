# Singularity container for the SDP Algorithm Reference Library

This is a project to create a Singularity container for the [SDP Algorithm Reference library](https://github.com/SKA-ScienceDataProcessor/algorithm-reference-library)

# Obtaining container

To download container run 

`singularity pull --name arl_container.simg shub://TMCantwell/ARL_container:latest
`
# Usage

To run ARL notebooks shell into the container

`
singularity shell arl_container.simg
`

You will need to source the environment file

`source /.singularity.d/env/90-environment.sh
`

start the arl environment

`
start-arlvenv
`

cd to the algorithm reference library notebooks and start jupyter notebook

`
cd /algorithm-reference-library/workflows/notebooks
jupyter notebook --no-browser --port=1895
`
