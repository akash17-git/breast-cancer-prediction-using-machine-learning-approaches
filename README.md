# Data Analysis Project

## REMOVING OUTLIERS
for i in range(0,len(numeric_col)):
    # IQR
    Q1 = np.percentile(df[numeric_col[i]], 25,
                      interpolation = 'midpoint')
    
    Q3 = np.percentile(df[numeric_col[i]], 75,
                      interpolation = 'midpoint')
    IQR = Q3 - Q1
    
    print("Old Shape: ", df.shape)
    
    # Upper bound
    upper=Q3+1.5*IQR
    # Lower bound
    lower=Q1-1.5*IQR
    # Removing the outliers
    df = df[(df[numeric_col[i]] < upper) & (df[numeric_col[i]] > lower)]


    
print("New Shape: ", df.shape)

## 📁 Files
- `notebook.ipynb`: Main Jupyter Notebook containing the code and analysis.
- `data/dataset.csv`: Dataset used for the analysis.

## 🛠️ Tech Stack
- Python
- Pandas
- NumPy
- Matplotlib / Seaborn
- Scikit-learn
- Jupyter Notebook

## 🚀 How to Run
1. Clone the repository.
2. Ensure you have Python installed (preferably in a virtual environment).
3. Install the required packages:
   ```
   pip install -r requirements.txt
   ```
4. Launch the notebook:
   ```
   jupyter notebook notebook.ipynb
   ```

## 📌 Notes
- Make sure the `dataset.csv` is placed in a `data/` directory at the root level.
- All preprocessing and model steps are included within the notebook.

## 📍 Author
Akash – Data Science graduate | [GitHub Profile](https://github.com/akash17-git)
