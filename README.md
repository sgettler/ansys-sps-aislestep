# ANSYS SPS Terrace Aisle Step With Handrail

[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)

Generates a static model using shell elements and checks handrail loads. Macros
written in ANSYS APDL.

#### Installation and Use

To use the macros, clone this repo and use the `model` folder as your ANSYS
working directory. To build the model, run `01-00-Model.inp` and to solve the
static loading, run `02-00-Static.inp`.

Everything should work with ANSYS Mechanical, ANSYS Structural, or the
Structural Solver (though there is not yet any postprocessing function).

#### Parameters

Parameters for modifying the model geometry are found in the
`00-01-geoparams.inp` file. All dimensions are assumed to be in metres.

This version of the macro assumes that handrail bolts are in line with the
centreline of the step and an additional reinforcing plate is included below
the handrail baseplate. Given the variability of handrail location, geometry
must be updated manually to move this connection.

###### Aisle Step Dimensions
|Name|Description|
|----|-----------|
|STEP_L|length of the step|
|STEP_W|width or depth of the step|
|STEP_H|height of the step|
|STEP_T|plate thickness used to build the step|
|STEP_N|number of step treads|

###### Handrail Reinforcement
|Name|Description|
|----|-----------|
|STEP_PT|thickness of additional plate below handrail baseplate|
|STEP_PL|length of plate|
|STEP_PW|width of plate|

###### Handrail Baseplate Dimensions
|Name|Description|
|----|-----------|
|BASE_X|baseplate location along length|
|BASE_Y|baseplate location along width|
|BASE_Z|baseplate elevation|
|BASE_L|baseplate length (dimension parallel to step length)|
|BASE_W|baseplate width|
|BASE_T|baseplate thickness|
|BASE_BX|location of first bolt(s) along length|
|BASE_BY|location of first bolt(s) along width|
|BASE_BSX|spacing between bolts along length; if value is 0, only one row is created|
|BASE_BSY|spacing between bolts along width; if value is 0, only one row is created|

###### Handrail Post Dimensions
|Name|Description|
|----|-----------|
|RAIL_H|height of post (and therefore load application)|

Parameters for the loading are found in the `00-02-loadparams.inp` file. The
default loading is 200lbs concentrated load on the post per ICC-300.
