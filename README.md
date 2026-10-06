# PyWIB

<p align="center">
  <img src="docs/source/_static/images/logo-pywib.svg" alt="Interaction Lab logo" width="120">
</p>

Pywib (Python Web Interaction Behaviour) is a library desgined for analysing and obtaning metrics from users interaction with web pages.

## How to

To install PyWIB, please use:

```bash
pip install pywib
```

A minimal example of how to use PyWIB is presented here. If you require deeper information about the librarys API please consult the [documentation](https://uniovi-hci.github.io/pywib/).

```python
from pywib import to_pywib_df, velocity, velocity_metrics, visualize_trace, ColumnNames

# Considering an already loaded CSV into a pandas DataFrame

df = to_pywib_df(df, "sessionIdCol", "xCoordinateCol", "yCoordinateCol", "timeStampCol", "eventTypeCol", "keyValueCol", "keyCodeCol").copy()

v = velocity(df, per_traces=True)
v_metrics = velocity_metrics(df=None, traces=v)

userSession = df[df[ColumnNames.SESSION_ID] == "USER_A"].copy()
visualize_trace(userSession, userSession.index, "USER_A", type="info", save_path="user_a_trace.png")
```

## Running the tests
First, navigate to the PyWIB folder
```bash
cd pywib
```

Then install the required dependencies using python, use a virtual environment if you wish to.
```python
pip install pytest
pip install -r requirements.txt
```
Then, run the tests using:
```python
pytest test
```

## Citation

If you use our tool in your research, we kindly ask you to cite us.

G. D. Carvajal-Aza, A. Alvarez-Varela, J. De Andres, M. Gonzalez-Rodriguez, D. Fernandez-Lanvin, and M. Paino, "PyWIB: A Python Library for a Multi-Modal Approach to Web Interaction Behavior Analysis," in *Proceedings of the 2026 IARIA Annual Congress on Frontiers in Science, Technology, Services, and Applications (IARIA Congress 2026)*, Nice, France, Jul. 2026, pp. 103–108. Available: https://www.thinkmind.org/library/IARIA_CONGRESS/IARIA_Congress_2026/iaria_congress_2026_1_170_50103.html


## Generating Documentation

For bulding the PyWIB documentation in your local device, use:

```
cd pywib/docs
make html
```

And then access `docs/build/html/index.html` to navigate.