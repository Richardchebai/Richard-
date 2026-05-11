    Healthcare Exploratory Data Analysis (EDA). 

Exploring patient data to identify patterns in hospital readmissions and improve healthcare outcomes.

           Project Overview
This project performs an in-depth exploratory data analysis on a hospital patient dataset. The goal is to understand the factors that contribute to patient readmissions within 30 days of discharge — a major challenge for healthcare systems worldwide. The insights from this analysis can help hospitals allocate resources more effectively and improve patient care. 

          Objectives

Explore demographic and clinical variables affecting readmission
Identify high-risk patient groups
Visualise patterns across age, diagnosis, and length of stay
Provide data-driven recommendations for reducing readmission rates. 

           Tools & Technologies

Python 
Pandas 
Seaborn
Matplotlib
Jupyter 

             Project Structure
healthcare-eda/
│
├── data/
│   ├── raw/               patient_id	age	gender	diagnosis	admission_date	discharge_date	length_of_stay_days	insurance	follow_up_scheduled	readmitted_30_days
P001	72	Male	Heart Failure	03/01/2024	07/01/2024	4	Public	Yes	No
P002	45	Female	Diabetes	05/01/2024	08/01/2024	3	Private	No	Yes
P003	60	Male	Pneumonia	10/01/2024	15/01/2024	5	Public	Yes	No
P004	83	Female	Hip Fracture	12/01/2024	20/01/2024	8	Public	Yes	No
P005	55	Male	Diabetes	18/01/2024	20/01/2024	2	Private	No	Yes
P006	67	Female	Heart Failure	22/01/2024	27/01/2024	5	Public	Yes	No
P007	34	Male	Appendicitis	01/02/2024	04/02/2024	3	Private	Yes	No
P008	78	Female	Stroke	05/02/2024	12/02/2024	7	Public	No	Yes
P009	50	Male	Hypertension	09/02/2024	11/02/2024	2	Private	Yes	No
P010	65	Female	Heart Failure	14/02/2024	19/02/2024	5	Public	No	Yes
P011	42	Male	Diabetes	20/02/2024	23/02/2024	3	Private	No	Yes
P012	71	Female	Pneumonia	25/02/2024	01/03/2024	5	Public	Yes	No
P013	88	Male	Hip Fracture	02/03/2024	11/03/2024	9	Public	Yes	No
P014	56	Female	Hypertension	06/03/2024	08/03/2024	2	Private	Yes	No
P015	63	Male	Heart Failure	10/03/2024	16/03/2024	6	Public	No	Yes
P016	29	Female	Appendicitis	15/03/2024	18/03/2024	3	Private	Yes	No
P017	74	Male	Stroke	20/03/2024	28/03/2024	8	Public	No	Yes
P018	48	Female	Diabetes	01/04/2024	04/04/2024	3	Private	No	Yes
P019	80	Male	Heart Failure	05/04/2024	11/04/2024	6	Public	Yes	No
P020	37	Female	Pneumonia	08/04/2024	12/04/2024	4	Private	Yes	No
P021	66	Male	Hypertension	14/04/2024	16/04/2024	2	Public	Yes	No
P022	79	Female	Hip Fracture	18/04/2024	26/04/2024	8	Public	No	Yes
P023	53	Male	Diabetes	22/04/2024	25/04/2024	3	Private	No	Yes
P024	70	Female	Heart Failure	02/05/2024	08/05/2024	6	Public	Yes	No
P025	44	Male	Stroke	06/05/2024	12/05/2024	6	Private	Yes	No
P026	85	Female	Pneumonia	10/05/2024	17/05/2024	7	Public	No	Yes
P027	58	Male	Hypertension	15/05/2024	17/05/2024	2	Private	Yes	No
P028	69	Female	Diabetes	20/05/2024	23/05/2024	3	Public	No	Yes
P029	76	Male	Heart Failure	03/06/2024	09/06/2024	6	Public	Yes	No
P030	40	Female	Appendicitis	07/06/2024	10/06/2024	3	Private	Yes	No
P031	62	Male	Hip Fracture	12/06/2024	20/06/2024	8	Public	No	Yes
P032	55	Female	Stroke	16/06/2024	23/06/2024	7	Public	No	Yes
P033	47	Male	Diabetes	01/07/2024	04/07/2024	3	Private	No	Yes
P034	73	Female	Heart Failure	05/07/2024	11/07/2024	6	Public	Yes	No
P035	82	Male	Pneumonia	09/07/2024	15/07/2024	6	Public	No	Yes
P036	38	Female	Hypertension	14/07/2024	16/07/2024	2	Private	Yes	No
P037	67	Male	Diabetes	20/07/2024	23/07/2024	3	Public	No	Yes
P038	77	Female	Hip Fracture	02/08/2024	11/08/2024	9	Public	Yes	No
P039	52	Male	Stroke	06/08/2024	13/08/2024	7	Private	Yes	No
P040	60	Female	Heart Failure	10/08/2024	16/08/2024	6	Public	No	Yes
P041	43	Male	Appendicitis	15/08/2024	18/08/2024	3	Private	Yes	No
P042	71	Female	Diabetes	22/08/2024	25/08/2024	3	Public	No	Yes
P043	84	Male	Pneumonia	03/09/2024	10/09/2024	7	Public	No	Yes
P044	56	Female	Hypertension	07/09/2024	09/09/2024	2	Private	Yes	No
P045	68	Male	Heart Failure	12/09/2024	18/09/2024	6	Public	Yes	No
P046	35	Female	Appendicitis	18/09/2024	21/09/2024	3	Private	Yes	No
P047	75	Male	Stroke	01/10/2024	09/10/2024	8	Public	No	Yes
P048	49	Female	Diabetes	05/10/2024	08/10/2024	3	Private	No	Yes
P049	80	Male	Heart Failure	10/10/2024	17/10/2024	7	Public	Yes	No
P050	64	Female	Hip Fracture	15/10/2024	24/10/2024	9	Public	No	Yes

│   └── cleaned/           patient_id	age	gender	diagnosis	admission_date	discharge_date	length_of_stay_days	insurance	follow_up_scheduled	readmitted_30_days	age_group	high_risk	insurance_encoded	follow_up_encoded	readmitted_encoded
P001	72	Male	Heart Failure	03/01/2024	07/01/2024	4	Public	Yes	No	65+	Yes	0	1	0
P002	45	Female	Diabetes	05/01/2024	08/01/2024	3	Private	No	Yes	45-64	Yes	1	0	1
P003	60	Male	Pneumonia	10/01/2024	15/01/2024	5	Public	Yes	No	45-64	No	0	1	0
P004	83	Female	Hip Fracture	12/01/2024	20/01/2024	8	Public	Yes	No	65+	Yes	0	1	0
P005	55	Male	Diabetes	18/01/2024	20/01/2024	2	Private	No	Yes	45-64	Yes	1	0	1
P006	67	Female	Heart Failure	22/01/2024	27/01/2024	5	Public	Yes	No	65+	Yes	0	1	0
P007	34	Male	Appendicitis	01/02/2024	04/02/2024	3	Private	Yes	No	18-44	No	1	1	0
P008	78	Female	Stroke	05/02/2024	12/02/2024	7	Public	No	Yes	65+	Yes	0	0	1
P009	50	Male	Hypertension	09/02/2024	11/02/2024	2	Private	Yes	No	45-64	No	1	1	0
P010	65	Female	Heart Failure	14/02/2024	19/02/2024	5	Public	No	Yes	65+	Yes	0	0	1
P011	42	Male	Diabetes	20/02/2024	23/02/2024	3	Private	No	Yes	18-44	Yes	1	0	1
P012	71	Female	Pneumonia	25/02/2024	01/03/2024	5	Public	Yes	No	65+	No	0	1	0
P013	88	Male	Hip Fracture	02/03/2024	11/03/2024	9	Public	Yes	No	65+	Yes	0	1	0
P014	56	Female	Hypertension	06/03/2024	08/03/2024	2	Private	Yes	No	45-64	No	1	1	0
P015	63	Male	Heart Failure	10/03/2024	16/03/2024	6	Public	No	Yes	45-64	Yes	0	0	1
P016	29	Female	Appendicitis	15/03/2024	18/03/2024	3	Private	Yes	No	18-44	No	1	1	0
P017	74	Male	Stroke	20/03/2024	28/03/2024	8	Public	No	Yes	65+	Yes	0	0	1
P018	48	Female	Diabetes	01/04/2024	04/04/2024	3	Private	No	Yes	45-64	Yes	1	0	1
P019	80	Male	Heart Failure	05/04/2024	11/04/2024	6	Public	Yes	No	65+	Yes	0	1	0
P020	37	Female	Pneumonia	08/04/2024	12/04/2024	4	Private	Yes	No	18-44	No	1	1	0
P021	66	Male	Hypertension	14/04/2024	16/04/2024	2	Public	Yes	No	65+	No	0	1	0
P022	79	Female	Hip Fracture	18/04/2024	26/04/2024	8	Public	No	Yes	65+	Yes	0	0	1
P023	53	Male	Diabetes	22/04/2024	25/04/2024	3	Private	No	Yes	45-64	Yes	1	0	1
P024	70	Female	Heart Failure	02/05/2024	08/05/2024	6	Public	Yes	No	65+	Yes	0	1	0
P025	44	Male	Stroke	06/05/2024	12/05/2024	6	Private	Yes	No	18-44	No	1	1	0
P026	85	Female	Pneumonia	10/05/2024	17/05/2024	7	Public	No	Yes	65+	Yes	0	0	1
P027	58	Male	Hypertension	15/05/2024	17/05/2024	2	Private	Yes	No	45-64	No	1	1	0
P028	69	Female	Diabetes	20/05/2024	23/05/2024	3	Public	No	Yes	65+	Yes	0	0	1
P029	76	Male	Heart Failure	03/06/2024	09/06/2024	6	Public	Yes	No	65+	Yes	0	1	0
P030	40	Female	Appendicitis	07/06/2024	10/06/2024	3	Private	Yes	No	18-44	No	1	1	0
P031	62	Male	Hip Fracture	12/06/2024	20/06/2024	8	Public	No	Yes	45-64	Yes	0	0	1
P032	55	Female	Stroke	16/06/2024	23/06/2024	7	Public	No	Yes	45-64	Yes	0	0	1
P033	47	Male	Diabetes	01/07/2024	04/07/2024	3	Private	No	Yes	45-64	Yes	1	0	1
P034	73	Female	Heart Failure	05/07/2024	11/07/2024	6	Public	Yes	No	65+	Yes	0	1	0
P035	82	Male	Pneumonia	09/07/2024	15/07/2024	6	Public	No	Yes	65+	Yes	0	0	1
P036	38	Female	Hypertension	14/07/2024	16/07/2024	2	Private	Yes	No	18-44	No	1	1	0
P037	67	Male	Diabetes	20/07/2024	23/07/2024	3	Public	No	Yes	65+	Yes	0	0	1
P038	77	Female	Hip Fracture	02/08/2024	11/08/2024	9	Public	Yes	No	65+	Yes	0	1	0
P039	52	Male	Stroke	06/08/2024	13/08/2024	7	Private	Yes	No	45-64	No	1	1	0
P040	60	Female	Heart Failure	10/08/2024	16/08/2024	6	Public	No	Yes	45-64	Yes	0	0	1
P041	43	Male	Appendicitis	15/08/2024	18/08/2024	3	Private	Yes	No	18-44	No	1	1	0
P042	71	Female	Diabetes	22/08/2024	25/08/2024	3	Public	No	Yes	65+	Yes	0	0	1
P043	84	Male	Pneumonia	03/09/2024	10/09/2024	7	Public	No	Yes	65+	Yes	0	0	1
P044	56	Female	Hypertension	07/09/2024	09/09/2024	2	Private	Yes	No	45-64	No	1	1	0
P045	68	Male	Heart Failure	12/09/2024	18/09/2024	6	Public	Yes	No	65+	Yes	0	1	0
P046	35	Female	Appendicitis	18/09/2024	21/09/2024	3	Private	Yes	No	18-44	No	1	1	0
P047	75	Male	Stroke	01/10/2024	09/10/2024	8	Public	No	Yes	65+	Yes	0	0	1
P048	49	Female	Diabetes	05/10/2024	08/10/2024	3	Private	No	Yes	45-64	Yes	1	0	1
P049	80	Male	Heart Failure	10/10/2024	17/10/2024	7	Public	Yes	No	65+	Yes	0	1	0
P050	64	Female	Hip Fracture	15/10/2024	24/10/2024	9	Public	No	Yes	45-64	Yes	0	0	1

│
├── notebooks/
│   └── healthcare_eda.ipynb    
│
├── visuals/               charts and floats
│
└── README.md
               Key Findings

-Patients aged 65 and above had the highest readmission rates (34%)
-Diabetes and heart failure were the most common diagnoses among readmitted patients
-Patients with a length of stay under 3 days were more likely to be readmitted
-Missing follow-up appointments was strongly correlated with readmission. 

📊 Sample Visuals. 

📬 Contact
Richie — LinkedIn · Email