Here's a README file that provides an overview of the code, instructions for usage, and details about the functions:

---

# Hydrogen Bond Analysis And Visualization

This repository contains Python code for analyzing and visualizing hydrogen bond data from molecular simulations. The code reads data files, processes hydrogen bond information, and generates heatmaps for visual inspection.

## File Structure

- `main.py`: Contains the functions for processing and plotting hydrogen bond data.
- `README.md`: This file, providing an overview and instructions for usage.

## Requirements

To run the code, ensure you have the following Python packages installed:

- `numpy`
- `matplotlib`
- `pandas`
- `seaborn`

You can install these packages using `pip`:

```bash
pip install numpy matplotlib pandas seaborn
```

## Code Overview

### Functions

#### `hbond(system, run, resid_pair, donor_acceptor_pair, resolution)`

Calculates hydrogen bond data for a specific run and residue pair.

**Arguments:**

- `system` (str): Name of the system directory within the prefix path.
- `run` (int): Run number to specify the dataset.
- `resid_pair` (str): Residue pair identifier to locate the correct data file.
- `donor_acceptor_pair` (str): The specific donor-acceptor pair to match in column names.
- `resolution` (int): Interval for downsampling the data.

**Returns:**

- `list`: Downsampled list of hydrogen bond values.

#### `hbond_avg(system, run, resid_pair, donor_acceptor_pair)`

Computes the average of hydrogen bond values for a specific run and residue pair.

**Arguments:**

- `system` (str): Name of the system directory within the prefix path.
- `run` (int): Run number to specify the dataset.
- `resid_pair` (str): Residue pair identifier to locate the correct data file.
- `donor_acceptor_pair` (str): The specific donor-acceptor pair to match in column names.

**Returns:**

- `float`: Average of hydrogen bond values.

#### `hbond_plot(system, resid_pair, donor_acceptor_pair, n_replicates, resolution)`

Generates a heatmap of hydrogen bond values across different replicates and saves it as a PDF.

**Arguments:**

- `system` (str): Name of the system directory within the prefix path.
- `resid_pair` (str): Residue pair identifier to locate the correct data file.
- `donor_acceptor_pair` (str): The specific donor-acceptor pair to match in column names.
- `n_replicates` (int): Number of replicate runs to include in the plot.
- `resolution` (int): Interval for downsampling the data.

**Returns:**

- `None`

**Output:**

- Saves a heatmap of hydrogen bond values as a PDF in the specified directory.

## Usage

1. **Set the Prefix Path**

   Update the `prefix` variable in `main.py` to point to the root directory containing your data files.

2. **Call the Functions**

   Use the `hbond_plot` function to generate and save a heatmap. For example:

   ```python
   hbond_plot("fprdel84", "74-17", "U_16@O4-PRF_72@N2", 3, 20)
   ```

   This call will:

   - Use the data from the specified system and residue pair.
   - Include data from three replicates.
   - Downsample the data with an interval of 20.

3. **View Results**

   The resulting heatmap will be saved as a PDF in the directory specified by the `prefix` variable.

## Example

Here's a sample call to generate a heatmap:

```python
hbond_plot("fprdel84", "74-17", "U_16@O4-PRF_72@N2", 3, 20)
```

This will create a heatmap for the specified residue pair, using data from three replicate runs, and save it to the appropriate directory.

## Contributing

Feel free to contribute by opening issues or submitting pull requests. If you have suggestions or improvements, your input is welcome!

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

---

This README provides a clear and concise explanation of how to use the code, the purpose of each function, and the steps needed to generate the desired output.
