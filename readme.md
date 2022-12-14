# ezsaver
Lightweight tool to simplify saving/loading stuff in Python.

## Installation
Install with pip

    pip install ezsaver

## Usage
Import ezsaver as `ez`, and use `ez.save()` to save data. It will save objects of any complexity like tensorflow models, multidimensional numpy arrays, etc. Just feed it your filepath and the names of all the variables you want to save as arguments:

    import ezsaver as ez

    data1 = 2
    data2 = np.random.random(size=(2, 4))
    ez.save(filepath, data1, data2)

To load the data later, use `ez.load()`, giving it the filepath as an argument. It returns a dict, where the keys are the names of the original variables. If you forget what you named a variable, just view `loaded_data.keys()` to see them all.:

    loaded_data = ez.load(filepath)

    # keys are same name as original variables
    data1 = loaded_data['data1']
    data2 = loaded_data['data2']

If you have a feature request or problem, please open an issue. Note because of complexities of Python, ezsave does not work if you are coding directly from the command line .

## Acknowledgments
- Powered by the [joblib](https://github.com/joblib/joblib) and [varname](https://github.com/pwwang/python-varname) libraries.
- Thanks to [pwwang](https://github.com/pwwang) (developer of varname) for help debugging the earliest iteration.
- Developed with support from NIH Bioinformatics and NIEHS Neurobehavioral Core.
