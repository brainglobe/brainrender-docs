# Supported data types

| Data type | Actor | Accepted data format | File formats |  |
| :--- | :--- | :--- | :--- | :--- |
| Cell coordinates | Point, Points | numpy array | .npy, .h5 |  |
| Neuron morphology | Neuron | Mesh, morphapi.Neuron | **.swc** |  |
| Image \(3D\) | Volume,  Actor | numpy array | .npy,  .tiff |  |
| Streamlines | Streamlines | pandas DataFrame | .json, .h5 |  |

**Accepted data format:** the `Actor` classes for the data type expect the data in specific formats, this column illustrates what they expect.

**File formats:** example file formats that data can be stored in. When bold it means that the class can load the data from files directly. Check out [Using your data](./) to see how to load data and process it for brainrender.

