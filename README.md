# Crime in São Paulo: Geolocation Analysis

## Overview
This project involves analyzing crime data in **São Paulo** using geolocation information to identify patterns of theft and robbery. The dataset comprises multiple Excel and CSV files with information on crimes such as latitude, longitude, nature of the crime, and more.

I strongly advise checking the code via nbviewer since the folium package is not supported on GitHub. [Link](https://nbviewer.org/github/lucasjmorgado/DA-Crime-in-Barra-Funda/blob/main/Crime_in_Sao_Paulo.ipynb)

### Key Features:
- Geospatial visualization of crime data.
- Heatmaps and marker clusters to display crime density.
- Focus on specific neighborhoods (e.g., Barra Funda).

### Geolocation Focus:
The geolocation data in this project enables mapping the exact locations of crimes. We use the **latitude** and **longitude** coordinates to visualize crime hot spots and analyze spatial patterns. Specifically:
- **Heatmaps**: Show areas with high concentrations of crimes such as robbery and theft.
- **Marker Clusters**: Display individual crime occurrences in dense areas using interactive map markers.

## Project Structure
### Data
- **Source**: [São Paulo Public Security Secretariat Data](https://www.ssp.sp.gov.br/estatistica/consultas)
- **Excel to CSV conversion**: The crime data is provided in `.xlsx` format. For efficiency, it is converted to `.csv` to speed up processing.
- **Data Fields**: 
  - `CIDADE`: City where the crime occurred.
  - `DATA_OCORRENCIA_BO`: Date of occurrence.
  - `HORA_OCORRENCIA_BO`: Time of occurrence.
  - `BAIRRO`: Neighborhood of the crime.
  - `LOGRADOURO`: Street address.
  - `LATITUDE`, `LONGITUDE`: Geographical coordinates of the crime.
  - `NATUREZA_APURADA`: Type of crime (e.g., robbery, theft).

### Data Processing
1. **Loading Crime Data**: The data from multiple years is combined into a single DataFrame to facilitate analysis.
2. **Filtering Crime Data**: We focus on a specific neighborhood (Barra Funda) and filter data for thefts (`FURTO`) and robberies (`ROUBO`).
3. **Handling Missing Data**: Rows without latitude or longitude are excluded to ensure accuracy in mapping.

### Visualization
We use **Folium**, a Python library for geospatial data visualization, to create interactive maps that highlight crime distribution.

#### 1. **Robbery Map (Barra Funda)**
   - Marker clusters show exact robbery locations in Barra Funda.
   - Heatmaps illustrate robbery density across the neighborhood.

#### 2. **Theft Map (Barra Funda)**
   - Similar to the robbery map, marker clusters and heatmaps are used to visualize theft locations.

#### Examples:
  - You can check this and other maps interactively using this link: [Link](https://nbviewer.org/github/lucasjmorgado/DA-Crime-in-Barra-Funda/blob/main/Crime_in_Sao_Paulo.ipynb)

![Heatmap](https://raw.githubusercontent.com/lucasjmorgado/DA-Crime-in-Barra-Funda/refs/heads/main/heatmap_barrafunda_roubos.png)
![Cluster](https://raw.githubusercontent.com/lucasjmorgado/DA-Crime-in-Barra-Funda/refs/heads/main/MarkerCluster_barrafunda_roubos.png)

## How to Run
1. Convert the raw Excel data to CSV using the provided script:
   ```python
   df = pd.read_excel('/content/SPDadosCriminais_2022.xlsx')
   df.to_csv('SPDadosCriminais_2022.csv', index=False)
   ```

2. Load the crime data from the CSV files, filtering by relevant columns:
   ```python
   excel_files = ['/content/SPDadosCriminais_2024.csv', '/content/SPDadosCriminais_2023.csv', '/content/SPDadosCriminais_2022.csv']
   for file_name in excel_files:
       df = pd.read_csv(file_name, usecols=['CIDADE', 'LATITUDE', 'LONGITUDE', 'NATUREZA_APURADA', ...])
   ```

3. Execute Code:
   - Run every cell and look for the dashboards created in the code.

## Dependencies
- Python 3.x
- Pandas
- Folium
- Jupyter Notebook/Google Colab

## Conclusion
This analysis provides a visual representation of crime occurrences in **São Paulo**, using geolocation data to help authorities and citizens understand areas with higher crime rates, aiding in prevention and resource allocation.

---

### Summary of Changes
1. Corrected "Sao Paulo" to "São Paulo" consistently.
2. Changed "to check the code" to "checking the code" for better flow.
3. Minor punctuation adjustments for clarity. 

Let me know if you need any more help!
