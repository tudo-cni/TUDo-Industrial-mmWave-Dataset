# Performance Evaluation of IRS-enhanced mmWave Connectivity for 6G Industrial Networks - Dataset
This repository contains raw data of measurements conducted for the joint publication of TU Dortmund, Ericsson GmbH and Fraunhofer IPT: 

M. Danger et al., “Performance Evaluation of IRS-enhanced mmWave Connectivity for 6G Industrial Networks,” *2024 IEEE International Symposium on Measurement and Networking (IEEE M&N 2024)*, 2024

> [!IMPORTANT]  
> If you use this dataset, please reference the publication. You can find an example bibtex file [here](TUDo_Industrial_mmWave.bib).

Results are separated in the following file types:

- "positions_[...].csv": position (, multi-user scenario) and start time (**UTC+1**) of each measurement. Positions and scenario identifiers can be referenced from the publication 
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
