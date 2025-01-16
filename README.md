# Data-on-Plastic-Chemicals-in-Bay-Area-Foods

This Dash application analyzes data on plastic chemical levels in Bay Area foods. It provides interactive visualizations through tabs to explore the dataset, focusing on chemical concentrations, tag frequencies, and product collection locations.

## Key Functionalities: ##
1. **Data Cleaning and Preprocessing:**
    - Converts chemical concentration values (e.g., DEHP, DBP) from strings with `<` or `>` symbols to numeric values for analysis.
    - Removes outliers to ensure reliable visualizations.
    - Drops columns with more than 20% missing data for better usability.
    - Extracts latitude and longitude coordinates for visualization on a map using geocoding.
2. **Dash Application Layout:**
    - ***Scatter Matrix:*** Displays relationships between different chemical concentrations.
    - ***Tags Analysis:*** Shows the frequency of the most common tags associated with products.
    - ***Locations Map:*** Maps the collection locations of the products.
    - ***Individual Feature Analysis:*** Allows exploration of specific chemical concentration distributions via a dropdown menu.
3. Interactive Callbacks:
    - Updates visualizations dynamically based on user interaction with the tabs or dropdown menus.

## Explanation of Visualizations: ##
1. **Scatter Matrix (Scatter Matrix of Chemical Levels):**
    - ***Purpose:*** Examines correlations and relationships between different chemical concentrations in food products.
    - ***Interpretation:*** Diagonal plots show the distributions of individual chemical levels, while off-diagonal scatter plots reveal how two chemicals vary relative to one another.
2. **Tags Analysis (Top 10 Tag Frequency):**
    - ***Purpose:*** Highlights the most common tags (e.g., product types or categories) in the dataset.
    - ***Interpretation:*** A bar chart where the x-axis shows the tags, and the y-axis indicates their frequency, providing insights into prevalent product categories.
3. **Locations Map (Map of Product Locations):**
    - ***Purpose:*** Visualizes the geographic distribution of product collection locations.
    - ***Interpretation:*** Each point represents a product, with its geographic location determined by the geocoded `collected_at` field. Useful for identifying spatial trends in sampling.
4. **Individual Feature Analysis (Distribution of Selected Chemical):**
    - ***Purpose:*** Displays the distribution of a selected chemical (e.g., DEHP or DBP) to analyze concentration levels in products.
    - ***Interpretation:*** A histogram showing the frequency of specific concentration ranges. Peaks indicate common values, and the spread reflects variability.
  
## Code Enhancements and Insights: ##
- **Error Handling:** Includes error messages for missing latitude and longitude data, ensuring robust map rendering.
- **Geocoding:** Uses the geopy library to translate addresses into coordinates, enabling map visualizations.
- **Modularity:** Implements callbacks for each tab, ensuring clean and maintainable code.
- **Styling:** Utilizes Plotly's OpenStreetMap for location mapping, enhancing user interaction with intuitive zoom and pan features.
