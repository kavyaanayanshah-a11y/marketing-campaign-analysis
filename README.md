

\---



\# ▶️ RUN EVERYTHING — STEP BY STEP (copy-paste order)



```bash

\# 1) Go to project

cd marketing-campaign-analysis



\# 2) Activate virtual env

venv\\Scripts\\activate                # Windows

\# source venv/bin/activate           # Mac/Linux



\# 3) Install libraries

pip install -r requirements.txt



\# 4) ✅ Place marketing\_data.csv + marketing\_data\_dictionary.csv into data/raw/



\# 5) Clean + EDA + segmentation

python src/01\_pipeline.py

\#   -> data/processed/marketing\_clean.csv

\#   -> reports/figures/\*.png



\# 6) Build SQL database

python src/load\_to\_sql.py

\#   -> marketing.db



\# 7) (Optional) Run the SQL analytics

python -c "import sqlite3;c=sqlite3.connect('marketing.db');\[print(r) for r in c.execute('SELECT \* FROM vw\_segment\_kpis')]"



\# 8) Launch dashboard

streamlit run app/app.py

\#   -> open http://localhost:8501

