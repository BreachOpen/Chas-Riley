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

### Investigating Insider Threat through Email Analysis

In this exercise, I was tasked with investigating a potential insider threat within an organization. An employee of this organization was suspected of selling the organization's secrets to the media. The employee's hard drive had been recovered, and my goal was to examine the data artifacts, specifically the deleted emails, to uncover any evidence of wrongdoing.

#### Objectives:

1. **Creating a Forensic Image of the Hard Drive:**
   - **Tool Used:** FTK Imager
   - **Task:** Use FTK Imager to create a forensic image of the recovered hard drive. Ensure the integrity of the evidence by using appropriate settings for image creation.
![Creating Forensic Image]()

2. **Analyzing the Forensic Image with Autopsy:**
   - **Tool Used:** Autopsy
   - **Task:** Use Autopsy to analyze the forensic image and recover deleted emails stored on the hard drive.
![Recovering Emails]()

3. **Extracting and Analyzing Email Metadata:**
   - **Tool Used:** Email Examiner / ExifDataView
   - **Task:** Use Email Examiner or ExifDataView to extract and analyze metadata from the recovered emails. Focus on obtaining sender, recipient, date, and time information.
![Metadata Extraction]()

4. **Identifying Evidence of Wrongdoing:**
   - **Objective:** Analyze the extracted email content and metadata to identify any evidence of wrongdoing, such as unauthorized sharing of confidential information.
![Evidence Identification]()

---

### Conclusion:
To complete this investigation, I created a forensic image, recovered deleted emails, and analyzed metadata to uncover potential evidence of a crime. FTK Imager, Autopsy, and Email Examiner/ExifDataView were the tools I used to identify the unauthorized sharing (no evidence of selling was found) of confidential information.

---

## Skills Demonstrated
- Data Acquisition
- Analysis
- Network Forensics
- Memory Forensics
- Registry Analysis

## Tools Used
- FTK Imager
- Autopsy
- ExifDataView

