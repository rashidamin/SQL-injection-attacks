
# SQLi-SDN Full Reproducibility Package

This repository provides complete reproducibility support for the hybrid CNN–KNN SQL Injection detection framework integrated with SDN.

## Datasets Used
- NSL-KDD (Network intrusion baseline)
- CSIC-2010 HTTP Dataset (SQL Injection specific)

⚠ Due to licensing restrictions, datasets must be downloaded manually.

## Steps to Reproduce

1. Install dependencies:
   pip install -r requirements.txt

2. Download datasets and place them in:
   data/raw/NSL_KDD/
   data/raw/CSIC_2010/

3. Run preprocessing:
   python preprocessing/preprocess_nsl_kdd.py
   python preprocessing/preprocess_csic.py

4. Train hybrid model:
   python models/train_hybrid.py

5. Evaluate:
   python models/evaluate.py

6. Run SDN testbed:
   sudo mn --custom sdn/mininet_topology.py --topo simpletopo
   ryu-manager sdn/ryu_controller.py
