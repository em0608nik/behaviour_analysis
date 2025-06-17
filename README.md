# Behaviour Analysis Repository

This repository contains resources and a Jupyter Notebook for analyzing behavioral data of users in the Eindhoven neighbourhoods Karpen, Acht, and Vredeoord. The goal is to analyze user data with the view to establishing a bike-sharing start-up that will improve connectivity and sustainability on an inter- and intra-neighbourhood scale. The repository includes dataset files, scripts, and instructions for running the analysis on Google Colab or your local machine.

---

## **How to Open the Notebook**

### **Using Google Colab**

1. **Open the Notebook in Colab**:

   * Navigate to the notebook on GitHub.
   * Click on the notebook file (`user_behaviour.ipynb`).
   * Click the **"Open in Colab"** button that appears at the top of the page once loading has finished or manually open the notebook in Google Colab by appending the following link:

     ```
     https://colab.research.google.com/github/em0608nik/behaviour_analysis/blob/main/user_behaviour.ipynb
     ```

2. **Run the Setup Code Block**:

   * To access the dataset files used in the Notebook, you would need to clone them along with the repository to the local Colab runtime. For that, run the code block with the following contents, found in the notebook (or copy and run it manually by yourself):

     ```python
     import os

     if 'google.colab' in str(get_ipython()):
         if not os.path.exists('behaviour_analysis'):
             !git clone https://github.com/em0608nik/behaviour_analysis.git
         %cd behaviour_analysis
     ```

3. **Run the Notebook**:

   * Once the repository is cloned, proceed to run the remaining cells in the notebook as needed.

---

### **Using Your Local Machine**

1. **Clone the Repository**:

   * Open a terminal and run:

     ```bash
     git clone https://github.com/em0608nik/behaviour_analysis.git
     cd behaviour_analysis
     ```

2. **Install Dependencies**:

   * Make sure you have Python installed along with the required packages. You can install the dependencies by running (this includes all libraries used in the analysis):

     ```bash
     pip install -r requirements.txt
     ```

3. **Run the Notebook**:

   * Open the notebook locally using Jupyter Notebook or Jupyter Lab:

     ```bash
     jupyter notebook user_behaviour.ipynb
     ```

---

## **Datasets Overview**

The `behaviour_analysis` folder contains the following datasets:

### **Datasets**:

* **`bike_lanes.geojson`**:

  * This file contains official bike lanes (red lanes) in Eindhoven.

* **`bus_stops_1.geojson`**:

  * Includes relevant bustops in the neighbourhoods and hotspots, such as shopping centres, bound to attract a lot of users. The data is from GoogleMaps Columns include:
    * `name`: Distinguishes between bus stops and electrical station
    * `longitute` and `latitude`: Location

* **`eindhoven.geojson`**:

  * Location of car charging stations (both public and private) in the targetted neighbourhoods.

 * **`electricity_grid.geojson`**:

  * Includes capacity areas, outlining the readyness of regions to facilitate new transport-related electricity usage, and mid-voltage stations, located in proximity to the trageted neighbourhoods.

* **`ev_stations.geojson`**:
  
  * Includes proposed locations for hubs for our start-up. Columns include:
     * `name`: Station ID code.
     * `description`: Tier of the station - either primary or secondary.
     * `lan` and `lon`: Coordinates.
    
* **`fietsenstallingen.xlsx`**:

  * Includes opening time for each day of the week of major bicycle parking lots in Eindhoven, acquired from https://data.eindhoven.nl/explore/dataset/fietsenstallingen/information/?disjunctive.naam_fietsenstalling&disjunctive.type_stalling&disjunctive.openingstijden_maandag&disjunctive.openingstijden_dinsdag&disjunctive.openingstijden_woensdag&disjunctive.openingstijds_donderdag&disjunctive.openingstijden_vrijdag&disjunctive.openingstijden_zaterdag&disjunctive.openingstijden_zondag 

* **`final_amenities.geojson`**:

  * Includes amenities in the area of interest, separated by function. Columns include:
     * `name`: Tpe/name of amenity.
     * `lan` and `lon`: Coordinates.

* **`starting_points_on.geojson`**:
  
  * Includes the random starting locations used in the route analysis.
  

---

## **Notebook Overview**

### **Purpose**:

The notebook `user_behaviour.ipynb` is designed to perform exploratory data analysis and visualization of behavioral data, as well as generate synthetic data of user behaviour in Eindhoven, due to the lack of publically acessible assets. It allows researchers to:

* Load and preprocess datasets.
* Analyze temporal behaviour of users based on amenity weights in the selected areas.
* Analyze busyness of bike routes in Eindhoven and their fleet demand based on amenity location and weight.
* Analyze electrical grid capacity of Eindhoven (specifically Karpen, Vredeoord, and Acht) with the view to establishing new charging stations.
* Visualize results and have interactive plots that facilitate exploratory analysis.
* Propose hypothetical station locations based on previous results.
* Calculate probability tables mimicing users' destination decision making.

