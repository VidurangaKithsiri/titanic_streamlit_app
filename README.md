# Titanic Survival — Streamlit + ML

End-to-end project: EDA → model training (Kaggle Titanic) → Streamlit app → deployment.

## Quickstart (Local)

1. **Install Python 3.10–3.12** and add to PATH.
2. In VS Code terminal:
   ```bash
   python -m venv .venv
   .venv\Scripts\activate  # Windows
   pip install --upgrade pip
   pip install -r requirements.txt
   ```
3. Put the Kaggle Titanic `train.csv` (or any Titanic-format CSV) at `data/dataset.csv`.
4. Run the app:
   ```bash
   streamlit run app.py
   ```

## Training

- The app will train and cache a model automatically if `model.pkl` is missing.
- Alternatively, run the notebook in `notebooks/model_training.ipynb` to train and save a model.

## Project Structure

```
app.py
requirements.txt
model.pkl              # created after first training
artifacts/metrics.json # created after first training
data/
  dataset.csv          # place your Titanic CSV here
notebooks/
  model_training.ipynb
.streamlit/
  config.toml
README.md
```

## Deployment (Streamlit Cloud)

1. Push this folder to **GitHub**.
2. On **share.streamlit.io** (Streamlit Community Cloud), create a new app:
   - Select the repo/branch
   - App file: `app.py`
   - Python version: 3.11 or compatible
3. Add any required **secrets** or **environment** settings (none needed here).
4. Deploy.

## Notes

- Expected columns: `Survived, Pclass, Sex, Age, SibSp, Parch, Fare, Embarked`.
- Extra columns are ignored.
- Best model is selected via cross-validation among Logistic Regression, Random Forest, and SVM.
