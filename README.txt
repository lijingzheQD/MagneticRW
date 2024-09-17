
Magnetic Random Walk Simulation for Oil and Water Wells
=======================================================

This project is an R-based implementation of a magnetic random walk simulation aimed at modeling oil and water well drilling. It takes into account various constraints like safety distances, magnetic influence, and stability, and generates both visualizations and data outputs.

Features:
---------
- Magnetic random walk simulation for channel locations.
- Visualization of well locations and random walk trajectories.
- Customizable parameters like step length, safety distance, and stability.
- Automatic generation of plots saved as JPG and PPT files.

Requirements:
-------------
The following R packages are required to run this project:
- dplyr
- export
- smoothr
- ggplot2
- SpatialExtremes
- akima

To install the required R packages, use the following command in R:

```
install.packages(c("dplyr", "export", "smoothr", "ggplot2", "SpatialExtremes", "akima"))
```

Installation:
-------------
Extract the zip file and run the main one.r


Usage:
------
1. Prepare the well data in RDS format. The script expects a file such as `myPts in use of real case.rds` that contains well location data (X, Y coordinates) and well types (oil, water, or non-channel).

2. Load and run the main simulation script in RStudio or an R environment. The script will:
   - Load well data and required functions.
   - Create the magnetic field database.
   - Simulate random walks for each well.
   - Generate and save plots showing the well layout and random walk paths.

3. The simulation will output:
   - `original magnetic database.jpg`: Initial magnetic database with well locations.
   - `plot1.ppt`: PowerPoint file with well distribution and random walk visualizations.

Parameters:
-----------
You can customize the following parameters in the script:

- `N.max`: Maximum number of steps for the random walk (default: 100).
- `StepLength`: Length of each step in the random walk (default: 30).
- `safetyDistance`: Minimum safety distance from non-channel wells (default: 50).
- `MagneticRadius`: Radius of influence for the magnetic field (default: 30).
- `stabilityIndex`: Controls the randomness of the walk. Higher values result in less randomness (default: 1).

Output:
-------
- `original magnetic database.jpg`: A plot showing the initial well layout with the magnetic field.
- `plot1.ppt`: PowerPoint file with random walk paths and well positions.
- Optionally, you can adjust the code to generate additional output formats or plots.

Project Structure:
------------------
```
repository-name/
│
├── functions/                    # Contains custom R functions used in the simulation
│   ├── 函数random_walk_2d，磁力随机行走函数.R
│   ├── 函数Build_magneticDatabase.R
│   ├── 函数rotation.R
│   ├── 函数addchannel.R
│   └── Function UpperLeftShift and LowerRightShift.R
│
├── data/                         # Sample input data (well locations, etc.)
│   └── myPts in use of real case.rds
│
├── output/                       # Generated plots and simulation results
│
├── README.txt                    # Project documentation
└── main_simulation_script.R      # Main script to run the simulation
```

Contributing:
-------------
If you want to contribute to this project:
1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes and commit them (`git commit -m 'Add new feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Open a Pull Request.

License:
--------
This project is licensed under the MIT License. See the `LICENSE` file for more details.
