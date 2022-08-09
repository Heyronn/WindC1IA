
# Windc1IA
WindClIA software generates automated classifications of the different wind states in a historical data set coming from EMAS, thus reducing the time of cleaning and sorting information from EMAS files. By studying large amounts of data, these classifications allow, for example, to quickly review the wind potential of different areas. The WindC1IA software generates wind state graphs and files that speed up the analysis performed by experts in the area using the [`gmm`](https://scikit-learn.org/stable/modules/mixture.html) algorithm. 

# Libraries used and their version:

- **xlrd==1.2.0**
- **XlsxWriter==3.0.3**
- **numpy==1.22.2**
- **matplotlib==3.5.1**
- **sklearn==0.0**
- **pandas==1.4.1**
- **matplotlib==3.5.1**
- **openpyxl==3.0.10**

# Functions:

Two types of functions are available, cleanup functions and processing functions.

## Clear functions:

- **clearDataProcess:** Removes the folders generated from a previous analysis process when the program is started again.

- **clearResults:** Removes the results from the Results folder when the process is restarted.

- **formats:** Allows the cleaning of the input data, removing the header, and the name of the station, regardless if it is at the beginning or the end, and fixes the date format. The generated files are saved in the newFormat1 folder.

- **mainFiles:** Creates the main folders for the program execution.

- **createFiles:** Creates the procedure folders at the start of the analysis.

- **months:** Arranges the order of execution of the files by month and separates each data by its corresponding month. The generated files are saved in the newFormat2 folder.

- **NaN:** Sets a whole row to NaN, if any data in the row is NaN from the foo.py file in the main folder.

- **ibxTrue:** Places the current index of each record in a different file.

- **idxTrue_clusters:** Gathers the index and the cluster type in a separate file.

- **results:** Generates the zip file by joining the files in the results folder.

- **info:** Collects operating system and data information.

- **oneFile:** Joins all files in the newFormat2 folder into a single xls file, with columns set to generate the foo file, going from polar to Cartesian coordinates.

## Execution functions

- **gmm:** Uses the algorithm called gaussian mixture model to be able to display the graphs representing the wind states.

- **gmmOne:** Generates one graph per cluster.

- **std:** Reads column 2 belonging to the classification of the idxTrue_clusters.xls file and then generates six binary columns depending on the type of classification.

- **inputAc:** Prepares an input file, gathering the date and time of each record, as well as gathering the six binary columns depending on the classification type of the program std_prod.

- **histogram:** Converts the xls file generated by input_ac.py to csv file, to later develop the final histogram.

- **interface:** Defines the user interface.

- **main:** Function that contains the order of execution of the functions.

# Installation
The Windc1IA software has two versions, one for Windows and one for Linux. To run the Windows version, you only need to run the *Windc1IA.exe* program. For the Linux version, you must have [`Python 3.10.1`](https://www.python.org/downloads/)  or higher. I have installed the libraries already mentioned as follows.

- **pip install xlrd==1.2.0**
- **pip install XlsxWriter==3.0.3**
- **pip install numpy==1.22.2**
- **pip install matplotlib==3.5.1**
- **pip install sklearn==0.0**
- **pip install pandas==1.4.1**
- **pip install matplotlib==3.5.1**
- **pip install openpyxl==3.0.10**

Once the libraries are installed, the *Windc1IA.py* file can be executed. It is essential to clarify that for the Windows version, it is not necessary to have Python installed nor to have the libraries installed for the execution of the *Windc1IA.exe* executable. If we want to run the *Windc1IA.py* program in Windows, we will have to install [`Python 3.10.1`](https://www.python.org/downloads/) or higher and install the libraries mentioned above.

# Execution
To execute the Windc1A software, we will have to execute either the *Windc1IA.exe* or the *Windc1IA.py*. Once executed, we will get three options.

- **Instructions (1):** Pressing button one will provide us with basic instructions for the execution and use of the program.

- **Start (2):** Pressing button two will ask us the number of clusters that must be taken into account for the program's execution and will start the process.

- **Exit (3):** Pressing button three will exit the program.

If it is the first time that the program is executed, the WindC1IA software will automatically create the folders Files and Results. To start the process, the files to be analyzed must be placed in the Files folder. It is essential to clarify that the input files to be analyzed must be of xls extension and must have the following format order of the columns: *Date, WindDir, GustDir, WindRail, WindRap, GustRap, AirTemp, HumRelative, PresBarometric, Precipitation, RadSolar and the name of the station.* Note that the station name column can be at the beginning or the end.

Example of the order of the columns:

![Example columns](./images/ExampleCols.png)

At the end of the program execution, the results will be displayed in the Results folder, together with a .zip file to store the results.

# Example Execution
Inside the folder Example of results are the folders Files and Results. In the folder Files, there is the file *ECOGUARDAS_ene_2020*, a test file that will allow the running of the software. Inside the folder called Results, we have the graphs generated by the software, spreadsheets for analyzing these graphs, and a zip file that will store all the results previously mentioned.

Once executed, the folder's Files and Results will be generated randomly. The file *ECOGUARDAS_ene_2020* must be placed inside the folder Files. After that, the procedure must be started, and the final results will be in the folder Results.