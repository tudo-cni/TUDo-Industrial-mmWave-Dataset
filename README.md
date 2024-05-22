# Abstract: Performance Evaluation of IRS-enhanced mmWave Connectivity for 6G Industrial Networks
Private networks are a key innovation in the ongoing 5G era and the anticipated 6G landscape. The utilization of mmWave spectrum shows great potential for improving reliability in mobile and mission-critical industrial applications. Despite promising advancements demonstrated in controlled labs, de- ploying mmWave networks poses technical challenges, especially in dense, metallic industrial environments. This highlights the critical need for industry stakeholders to overcome associated technical challenges, thereby ensuring that end-to-end perfor- mance meets tailored requirements. Facilitating the transition of laboratory-validated benchmarks into practical industrial environments, we deploy our STING Network Companion as a distributed KPI Monitoring and Control System in a large- scale industrial manufacturing environment. Our results confirm the robust performance of mmWave technology in large-scale industrial environments, providing reliable connectivity even in most NLOS conditions. In addition, the deployment of our passive IRS solution HELIOS demonstrates significant improve- ments through strategic placement, restoring LOS performance in obstructed locations seamlessly and therefore proving its applicability to real-world industrial applications. Our study validates the promising potential of mmWave frequencies to address challenges in realistic environments, thereby supporting its further adoption in industrial applications.

# Contents of this Repository
This repository contains raw data of measurements conducted for the joint publication of TU Dortmund, Ericsson GmbH and Fraunhofer IPT: 

M. Danger et al., “Performance Evaluation of IRS-enhanced mmWave Connectivity for 6G Industrial Networks,” *2024 IEEE International Symposium on Measurement and Networking (IEEE M&N 2024)*, 2024

> [!NOTE]  
> If you use this dataset, please reference the publication. You can find an example bibtex file [here](TUDo_Industrial_mmWave.bib).

## Dataset description
Results are separated in the following file types:

- "positions_[...].csv": position (, multi-user scenario) and start time (**UTC+1**) of each measurement. Positions and scenario identifiers can be referenced from the publication. 
- "STING_data_[...].csv": KPIs from distributed FR2-STING units (1 hour needs to be added to 'time' due to different time zone).
  - utilized columns: 
    - time: Timestamp (**UTC**), format example: 2024-03-27 13:57:27.867378+00:00
    - sting_id: UE identifier, format example: FR2-01
    - nr_dl_mcs: Downlink MCS of mmWave Cell
    - nr_ul_mcs: Uplink MCS of mmWave Cell
    - ss_rsrp: Synchronization Signal (SS) Reference Signal Received Power (RSRP) of mmWave Cell in dBm (-999 if invalid)
    - ss_rsrq: Synchronization Signal (SS) Reference Signal Received Quality (RSRQ) of mmWave Cell in dBm (-999 if invalid)
    - ss_sinr: Synchronization Signal (SS) Signal to Interference and Noise Ratio (SINR) of mmWave Cell in dB (-999 if invalid)
    - tx_power: Transmission Power of mmWave Cell in dBm
    - direction: Transmission direction
    - datarate: Device throughput during per second in Mbit/s
    - num_stings: number of active STINGs in multi-user tests
    - test_name: long_term refers to multi-user, single_user to single user tests 
  - more modem data is extracted but unused in this analysis. Active and passive measurements are separated, resulting in some sparse rows. 

- "baseband_data_[...].csv": Centralized Baseband KPIs (1 hour needs to be added to 'time' due to different time zone).
  - utilized columns: 
    - tmpEpochsExec1: Unix Timestamp (**UTC**) 
    - MO: Mapping of New Radio Cell Distributed Unit (NRCellDU), only NRCellDU=1 rows are valid
    - pmRadioServingBeamDlDistr: Counter of activity per BeamID (Index). Activity is added from timestep to timestep until rollover.
      
# Acknowledgement
This work has been funded by the German Federal Ministry of Education and Research (BMBF) in the course of the 6G-ANNA project under grant no. 16KISK101 and the 6GEM Research Hub under the grant no. 16KISK038 as well as by the Ministry of Economic Affairs, Industry, Climate Action, and Energy of the State of North Rhine-Westphalia (MWIKE NRW) along with the Competence Center 5G.NRW under grant no. 005-01903-0047.
