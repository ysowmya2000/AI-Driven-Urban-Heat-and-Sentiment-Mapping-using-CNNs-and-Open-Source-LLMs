# AI-Driven-Urban-Heat-and-Sentiment-Mapping-using-CNNs-and-Open-Source-LLMs
This project demonstrates a **simulation-based AI pipeline** that integrates computer vision and natural-language processing to explore how **urban heat intensity** aligns with **public sentiment about heat**.  
It combines a **Convolutional Neural Network (CNN)** for super-resolving thermal imagery with an **open-source Large Language Model (LLM)** for sentiment classification on simulated social posts.



## Project Overview
Urban heat islands amplify temperature and discomfort in cities.  
To study this phenomenon safely and reproducibly, this project uses **synthetic (simulated)** data that mimics:
- Satellite-based **land surface temperature** measurements
- **Heat-related social media posts** from the public

The workflow fuses both datasets to analyze correlations between **physical heat** and **perceived heat** using deep learning and NLP.

---

## Tech Stack
| Domain | Tools / Libraries |
|--------|-------------------|
| Programming | Python (Jupyter Notebook) |
| Deep Learning | PyTorch |
| NLP / LLM | Hugging Face Transformers (DistilBERT) |
| Data Handling | NumPy, Pandas, SciPy |
| Visualization | Matplotlib, Folium (interactive map) |



## Workflow

### 1. Thermal Data Simulation
- Generated a **synthetic 128×128 temperature grid** representing urban land surface temperature.
- Downsampled and re-upsampled to create a **low-resolution** image mimicking MODIS data.
- Built training pairs for **super-resolution learning**.

### 2. CNN-Based Image Enhancement
- Implemented a lightweight **SRCNN-style model** (3 convolutional layers).
- Trained the CNN on overlapping image tiles to enhance spatial detail.
- Compared **bicubic interpolation vs CNN output** visually.

### 3. Social Text Simulation
- Created ~500 synthetic **heat-related social posts** across 10 days (e.g., *“It’s so hot today!”*).
- Randomized temperature and date fields to simulate real-world temporal patterns.

### 4. Sentiment & Persona Analysis
- Applied **DistilBERT** for binary sentiment classification (Positive / Negative).
- Added **rule-based persona tags** (e.g., commuter, resident, comfort seeker).

### 5. Correlation & Visualization
- Computed **daily mean temperature** and **negative sentiment ratio**.
- Measured correlation between heat intensity and negative emotion.
- Built:
  - *Time-series plots* (temperature vs sentiment)
  - *Interactive Folium map* of city sentiment distribution



## Outputs
1. **Heat Maps** — Before/after CNN enhancement  
2. **Correlation Plot** — Heat vs Negative Sentiment  
3. **Interactive Map** — `urban_heat_sentiment_map.html` (open in browser or inline)



## Key Results
- CNN enhancement produced sharper, more detailed temperature maps than interpolation alone.  
- Simulated sentiment data showed increasing negativity with higher daily temperatures.  
- Folium map visualized positive (green) and negative (red) posts spatially across city bounds.



## Skills Demonstrated
- Deep learning (CNN design and training)
- NLP and LLM-based sentiment classification
- Multimodal data fusion (image + text)
- Python data analysis and visualization
- Interactive geospatial mapping (Folium)
