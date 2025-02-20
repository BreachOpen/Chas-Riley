<div style="display: inline-block;">
  <a href="https://breachopen.github.io/Chas-Riley/">
    <img src="https://img.shields.io/badge/Home-3ba0e6" alt="Home">
  </a>
</div>

<div style="display: inline-block;">
  <a href="https://github.com/BreachOpen/Chas-Riley/" target="_blank">
    <img src="https://img.shields.io/badge/Github_Source-3ba0e6" alt="Github Source">
  </a>
</div>

---

### Corporate Network Breach Investigation

In this exercise, I was tasked with investigating a cybersecurity breach within a corporate network. The network in question was compromised, and my goal was to identify the source of the breach, analyze the affected systems, and gather digital evidence to support the investigation.

#### Objectives:

1. **Mounting the Forensic Image:**
   - **Tool Used:** Arsenal Image Mounter
   - **Task:** Mount the forensic image “CBARROW_Student.E01” using the default settings.
![Mounting the Image](../../assets/img/forensics/1.png)

2. **Adding the Logical Device with FTK Imager:**
   - **Tool Used:** FTK Imager
   - **Task:** Add the Logical device mounted with Arsenal Image Mounter and export the forensic image in E01 format with specified settings.
 ![Logical Device](../../assets/img/forensics/2.png)

3. **Adding the Physical Device with FTK Imager:**
   - **Tool Used:** FTK Imager
   - **Task:** Remove the current device and add the physical device mounted with Arsenal Image Mounter, then export the forensic image in E01 format with specified settings.
![Physical Device](../../assets/img/forensics/3.png)

4. **Creating a New Autopsy Case:**
   - **Tool Used:** Autopsy
   - **Task:** Create a new Autopsy case using “nps-2009-domexusers.e01” as a data source and let the case finish building.
![Autopsy Case](../../assets/img/forensics/4.png)

5. **Adding and Running Hash Lookup in Autopsy:**
   - **Tool Used:** Autopsy
   - **Task:** Add the hash set named “CYBV-388-Final-Hashset” and run the ingest module with selected hash lookup.
![Hash Lookup](../../assets/img/forensics/5.png)

6. **Processing Files with Exiftool:**
   - **Tool Used:** Exiftool
   - **Task:** Export files found by Autopsy and process them using Exiftool to extract metadata.
![Exiftool](../../assets/img/forensics/6.png)


7. **Analyzing Network Traffic with Wireshark:**
   - **Tool Used:** Wireshark
   - **Task:** Open Wireshark and analyze the affiliated network traffic.
![Wireshark Analysis](../../assets/img/forensics/7.png)

---

### Conclusion:
I identified the source of the breach and gathered digital evidence to support my conclusion. Each tool I used gave me valuable data, which helped me thoroughly investigate the breach. This project boosted my skills with forensic tools like Arsenal Image Mounter, FTK Imager, Autopsy, Exiftool, and Wireshark, and also gave me skillsets that could help me in other similar cybersecurity scenarios.

---

## Skills Demonstrated

- Data Acquisition
- Analysis
- Network Forensics
- Memory Forensics
- Registry Analysis
