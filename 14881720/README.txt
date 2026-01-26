-------------------
GENERAL INFORMATION
-------------------
1. Title:
Dataset of RTT latency internet measurements using Ripe Atlas anchor nodes in Europe.

2. Description of the dataset:
This dataset provides real-world Round-Trip Time (RTT) latency measurements collected from a distributed network of probing nodes (Monitors) to target IP addresses. It is designed for training and evaluating machine learning models for IP geolocation.

3. Authors:
Miguel A. Ortega, Alejandro S. Martínez, María D. Cano-Baños, Pilar Manzanares-López, Antonio J. Jara.

4. Author's contact information:
Miguel A. Ortega (miguelangel.ortega@edu.upct.es, ORCID: 0009-0000-4420-9672, Universidad Politécnica de Cartagena).

5. Date of data collection:
19-07-2024: Data collection for LearningDataset_RTT_RipeAtlasEU.csv
19-07-2024: Data collection for ValidationDataset_RTT_RipeAtlasEU.csv

6. Geographic location of data collection:
The RTT latency measurements were collected from 4 distributed Monitors located across different geographical regions in Europe.

7. Funding:
This research has been founded by the project R&D&I Lab in Cybersecurity, Privacy, and Secure Communications (TRUST Lab), financed by the European Union NextGeneration-EU, the Recovery Plan, Transformation and Resilience, through INCIBE.

8. Language of the dataset:
English

----------------------------------
SHARING/ACCESS/CONTEXT INFORMATION
----------------------------------
1. Usage Licenses/restrictions placed on the data:
CC-BY 4.0

--------------------
DATA & FILE OVERVIEW
--------------------
1. File List:
	- LearningDataset_RTT_RipeAtlasEU.csv: Training dataset (contains known IP locations).
	- ValidationDataset_RTT_RipeAtlasEU.csv: Evaluation dataset (contains IP locations known but treated as unknown for model testing).

2. File format:
	.csv

--------------------------
METHODOLOGICAL INFORMATION
--------------------------
1. Description of methods used for collection/generation of data:
Data were collected using a network of four Monitors deployed in different geographic locations. Each Monitor measured RTT latency to different Landmarks (known locations for training) and Target IPs (used for evaluation). The latency values were recorded for geolocation model training and validation.

- Learning Dataset (LearningDataset_RTT_RipeAtlasEU.csv):
Contains latency measurements to Landmarks (known locations).
Used for training machine learning models.

- Validation Dataset (ValidationDataset_RTT_RipeAtlasEU.csv):
Contains latency measurements to Target IPs (treated as unknown locations).
Used for model evaluation.

-------------------------
DATA-SPECIFIC INFORMATION
-------------------------
LearningDataset_RTT_RipeAtlasEU.csv
	1. Number of variables: 10
	2. Number of cases/rows: 3867
	3. Variable List:
		- measure_id: Unique identifier for each measurement.
		- anchor_id: ID of the target node to be geolocated.
		- dst_ip: IP address of the target node.
		- init_time: Timestamp of the measurement.
		- latency_m1 - latency_m4: RTT fingerprint vector (latency measurements from 4 Monitors) (milliseconds).
		- latitude, longitude: Ground truth geolocation of the target node.
	
ValidationDataset_RTT_RipeAtlasEU.csv
	1. Number of variables: 10
	2. Number of cases/rows: 1035
	3. Variable List:
		- measure_id: Unique identifier for each measurement.
		- anchor_id: ID of the target node to be geolocated.
		- dst_ip: IP address of the target node.
		- init_time: Timestamp of the measurement.
		- latency_m1 - latency_m4: RTT fingerprint vector (latency measurements from 4 Monitors) (milliseconds).
		- latitude_anchor, longitude_anchor: Ground truth geolocation of the target node (used only for evaluation, not as input to models).