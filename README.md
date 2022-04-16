# DataJoint Element - Experimental trials
This repository is a work in progress not yet ready for public release.
It serves as a draft of a DataJoint element for trialized experiments behavior
for our U24 initiative.

## Element architecture

In both of the following diagrams, the trial table starts immediately downstream from
***Session***. In one case, Sessions are first segmented into trials, and then 
segmented into events. This might be appropriate, for example, in a paradigm with 
repeated conditions and response behaviors associated with different conditions. In the 
next, Sessions are directly upstream from both Trials and Events. This might be appropropriate for a paradigm that recorded events within naturalistic free behavior. We  provide an
[example workflow](https://github.com/datajoint/workflow-trial/) with a
[pipeline script](https://github.com/datajoint/workflow-trial/blob/main/workflow_trial/pipeline.py)
that models combining this Element with the corresponding 
[Element-Session](https://github.com/datajoint/element-session).

### Trial & Event Schemas

![trial and event schemas](./images/trial_event_diagram.svg)

## Installation

+ Install `element-trial`
    ```
    pip install element-trial
    ```

+ Upgrade `element-trial` previously installed with `pip`
    ```
    pip install --upgrade element-trial
    ```

<!---
+ Install `element-interface`

    + `element-interface` is a dependency of `element-trial`, however it is not 
      contained within `requirements.txt`.

    ```
    pip install "element-interface @ git+https://github.com/datajoint/element-interface"
    ```
-->

## Usage

### Element activation

To activate the `element-trial`, one need to provide:

1. Schema names for the event or trial module
2. Upstream Session table: A set of keys identifying a recording session (see [
Element-Session](https://github.com/datajoint/element-session)).
3. Utility functions. See 
[example definitions here](https://github.com/datajoint/workflow-trial/blob/main/workflow_trial/paths.py)

For more detail, check the docstring of the `element-trial`:
```python
from element_trial import event, trial
help(event.activate)
help(trial.activate)
```

## Citation

+ If your work uses DataJoint and DataJoint Elements, please cite the respective Research Resource Identifiers (RRIDs) and manuscripts.

+ DataJoint for Python or MATLAB
    + Yatsenko D, Reimer J, Ecker AS, Walker EY, Sinz F, Berens P, Hoenselaar A, Cotton RJ, Siapas AS, Tolias AS. DataJoint: managing big scientific data using MATLAB or Python. bioRxiv. 2015 Jan 1:031658. doi: https://doi.org/10.1101/031658

    + DataJoint ([RRID:SCR_014543](https://scicrunch.org/resolver/SCR_014543)) - DataJoint for < Python or MATLAB > (version < enter version number >)

+ DataJoint Elements
    + Yatsenko D, Nguyen T, Shen S, Gunalan K, Turner CA, Guzman R, Sasaki M, Sitonic D, Reimer J, Walker EY, Tolias AS. DataJoint Elements: Data Workflows for Neurophysiology. bioRxiv. 2021 Jan 1. doi: https://doi.org/10.1101/2021.03.30.437358

    + DataJoint Elements ([RRID:SCR_021894](https://scicrunch.org/resolver/SCR_021894)) - Element Event (version < enter version number >)