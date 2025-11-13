### Post-processing and Plotting Results

After running the optimization, use the `PostProcessor` object to analyze and plot the empirical probabilities from the generated samples.

```python
from PostProcessing import PostProcessor
postprocessor = PostProcessor(samples_filename)
```

#### **Parameters:**

- **samples_filename** (_str_): The filename containing the generated samples data.

---

The PostProcessor object provides multiple methods. One is the `plot_empirical_probabilities` method, which generates a plot of the empirical probabilities for different tolerances.

```python
postprocessor.plot_empirical_probabilities(dpi=10, layout="32", tols=[1,2,3,4,5,6], running=False)
```

#### **Parameters:**

- **dpi** (_int_): Resolution of the plot, in dots per inch.
- **layout** (_str_): Layout of the plot, specified as a string. Must be one of `["13", "23", "32", "22"]` (default is `"23"`).
- **tols** (_list_): List of tolerances for computing empirical probabilities (default is `[1,2,3,4,5,6]`).
- **running** (_bool_): Whether to display the plot with a running average or not (default is `False`).

---

Another method is `compute_tables`, which generates tables of empirical means and standard deviations.

```python
postprocessor.compute_tables(measured=[K], dpi=100, mode="mean", running="True")
```

#### **Parameters:**

- **measured** (_list_): List with iteration counts to measure the empirical probabilities.
- **dpi** (_int_): Resolution of the plot, in dots per inch.
- **mode** (_str_): Mode for computing the tables, specified as a string. Must be one of `["mean", "std", "best"]` (default is `"mean"`).
- **running** (_bool_): Whether to display the results are computed with a running average or not (default is `True`).
