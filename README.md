# Student Performance Predictor

**Author:** Ricardo Alvarez

### Tool Choice & Justification
For this sprint, I utilized **Pandas** for my data wrangling layer and **Scikit-learn** for my modeling framework. Pandas provides immediate, intuitive DataFrame manipulation, which is essential for a fast-paced one-day sprint where rapid EDA and aggregations are prioritized over distributed computing. Scikit-learn was chosen because its `Pipeline` and `ColumnTransformer` APIs guarantee mathematical safety against data leakage during scaling and encoding. Furthermore, Scikit-learn provides out-of-the-box implementations of both Linear Regression and L2-regularized Logistic Regression, satisfying all assignment constraints in a unified ecosystem.

### Dataset
**Student Performance (UCI)**
* **Regression Target:** `G3` (Final Grade, 0-20)
* **Classification Target:** `pass` (Binary: 1 if G3 >= 10, else 0)
* *Note: I concatenated both the Math and Portuguese datasets to maximize my row count, and explicitly dropped G1 and G2 to prevent data leakage and make the machine learning task meaningful.*

### AI Usage Disclosure
* **Tool Used:** Google Gemini
* **Tasks Assisted With:**
  * Structuring the `pyproject.toml` dependencies and modifying the `Dockerfile` to correctly build the `.venv` virtual environment as required by the rubric.
  * Generating the boilerplate `matplotlib` and `seaborn` syntax for the three required EDA subplots.
  * Debugging a `FileNotFoundError` related to relative pathing inside the `.devcontainer` folder.
  * Assisting with the technical phrasing for the model interpretations (specifically explaining the impact of the '0' grade outliers in Linear Regression and how L2 regularization balanced the weights in Logistic Regression).

### Run Instructions
To clone and reproduce this repository using the DevContainer:
```bash
git clone https://github.com/Yuky145/Machine-Learning-6-SIN-A-Mar-Jul-2026.git

uv run jupyter notebook
