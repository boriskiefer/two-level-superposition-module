# Two-Level Hamiltonian Simulator

This archive contains the reference Jupyter simulator accompanying the manuscript:

**From Two-Level Hamiltonians to Quantum Superposition and Measurement: A Traceable Classroom Module**

The simulator is designed for classroom use with the five-activity sequence described in the manuscript and Supplementary Material.

## Contents

- `superposition_ajp_simulator.ipynb` - reference Jupyter notebook
- `requirements.txt` - Python package requirements
- `README.md` - this file

If the notebook is provided under a different filename, open that `.ipynb` file in JupyterLab and run the cells in order.

## Installation

Create or activate a Python environment, then install the required packages:

```bash
pip install -r requirements.txt
```

The required packages are:

```text
numpy
matplotlib
ipywidgets
jupyterlab
```

## Running the simulator

From the directory containing the notebook, start JupyterLab:

```bash
jupyter lab
```

Open the simulator notebook and run the cells in order.

The interactive dashboard appears after the main simulator cell is executed.

## Hamiltonian

The simulator uses the general two-level Hermitian Hamiltonian

```text
H = h0 I + hx sigma_x + hy sigma_y + hz sigma_z
```

The four sliders control the real parameters:

- `h0`
- `hx`
- `hy`
- `hz`

## Sampling controls

The sampling controls specify:

- the number of measurement shots `N`
- the random-number seed
- resampling of the current state
- reset to the default parameter values

## Displayed quantities

For the selected Hamiltonian, the simulator displays:

- Cartesian parameters `(h0, hx, hy, hz)`
- spherical parameters `(r, theta, phi)`
- the 2 x 2 Hamiltonian matrix
- eigenvalues `E-` and `E+`
- energy eigenstates expressed in the computational basis
- computational-basis amplitudes
- Born-rule probabilities
- finite-shot sampled frequencies
- the energy splitting `Delta E = E+ - E- = 2r`

The histogram shows sampled measurement frequencies together with the corresponding theoretical Born-rule probabilities.

## Degenerate case

When

```text
r = sqrt(hx^2 + hy^2 + hz^2) = 0
```

the Hamiltonian is proportional to the identity:

```text
H = h0 I
```

The two eigenvalues are then degenerate. The Hamiltonian does not select a unique eigenbasis, so the simulator reports the degeneracy rather than displaying arbitrary numerical eigenstates or measurement probabilities.

## Classroom use

The notebook may be used directly by students or projected by the instructor for a class-wide predict-observe-explain activity.

Students can first record written predictions, then compare them with the simulator output, and finally explain the relationship among the Hamiltonian, eigenstates, amplitudes, Born-rule probabilities, and finite measurement statistics.

## Notes

- The simulator uses standard two-level Hamiltonian and computational-basis conventions.
- Numerical eigensystem checks are performed internally.
- Finite-shot frequencies vary with the random seed and number of shots even when the Hamiltonian and theoretical probabilities are unchanged.

## Citation

If this simulator is used in teaching or adapted for other instructional work, please cite the accompanying manuscript.
