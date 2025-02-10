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

### Website Scraper

In this exercise, you are tasked with investigating a cybersecurity breach within a corporate network. The network has been compromised, and your goal is to identify the source of the breach, analyze the affected systems, and gather digital evidence to support the investigation.

#### Objectives:

1. **Mounting the Forensic Image:**
   - **Tool Used:** Arsenal Image Mounter
   - **Task:** Mount the forensic image “CBARROW_Student.E01” using the default settings.
   - **Screenshot:** ![Mounting the Image](insert_screenshot_here)

2. **Adding the Logical Device with FTK Imager:**
   - **Tool Used:** FTK Imager
   - **Task:** Add the Logical device mounted with Arsenal Image Mounter and export the forensic image in E01 format with specified settings.
   - **Screenshot:** ![Logical Device](insert_screenshot_here)

3. **Adding the Physical Device with FTK Imager:**
   - **Tool Used:** FTK Imager
   - **Task:** Remove the current device and add the physical device mounted with Arsenal Image Mounter, then export the forensic image in E01 format with specified settings.
   - **Screenshot:** ![Physical Device](insert_screenshot_here)

4. **Creating a New Autopsy Case:**
   - **Tool Used:** Autopsy
   - **Task:** Create a new Autopsy case using “nps-2009-domexusers.e01” as a data source and let the case finish building.
   - **Screenshot:** ![Autopsy Case](insert_screenshot_here)

5. **Adding and Running Hash Lookup in Autopsy:**
   - **Tool Used:** Autopsy
   - **Task:** Add the hash set named “CYBV-388-Final-Hashset” and run the ingest module with selected hash lookup.
   - **Screenshot:** ![Hash Lookup](insert_screenshot_here)

6. **Processing Files with Exiftool:**
   - **Tool Used:** Exiftool
   - **Task:** Export files found by Autopsy and process them using Exiftool to extract metadata.
   - **Screenshot:** ![Exiftool](insert_screenshot_here)

7. **Exporting Registry Hives:**
   - **Tool Used:** FTK Imager / Registry Explorer
   - **Task:** Export the registry hives located in “windows\system32\config” to a directory of your choice.
   - **Screenshot:** ![Registry Hives](insert_screenshot_here)

8. **Analyzing Network Traffic with Wireshark:**
   - **Tool Used:** Wireshark
   - **Task:** Open “nitroba.pcap” with Wireshark and analyze the network traffic.
   - **Screenshot:** ![Wireshark Analysis](insert_screenshot_here)

---

### Conclusion:

Summarize the findings of your investigation, highlighting the key pieces of evidence that identify the source of the breach, affected systems, and any relevant digital evidence supporting the investigation. Discuss the significance of the findings and how they contribute to understanding the cybersecurity breach within the corporate network.

---

## Skills Demonstrated

List the skills you demonstrated through your projects:

- Data Acquisition
- Analysis
- Network Forensics
- Memory Forensics
- Registry Analysis
