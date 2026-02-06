# Dicomaster Beginner Tutorial

This is a simple beginner-friendly example for Dicomaster.  
It demonstrates a typical research workflow for medical AI researchers:

1. DICOM dataset
2. Anonymization
3. Metadata extraction
4. CSV output
5. ML usage

---

## Step 1: Prepare your folders

- Input DICOM files folder: `sample_dicoms`
- Output folder for anonymized files: `anonymized_dicoms`

---

## Step 2: Python example using Dicomaster

```python
import dicomaster

# Input and output paths
input_folder = "sample_dicoms"
output_folder = "anonymized_dicoms"

# Dicomaster arguments
dicomaster_args = [
    "--batch", input_folder,
    "--output", "agg-csv",        # CSV output for ML or analysis
    "--output-dir", output_folder,
    "--anonymize",                 # Remove or pseudonymize patient data
    "--threads", "4"               # Adjust based on CPU cores
]

# Run Dicomaster
dicomaster.main(dicomaster_args)

print("✅ Workflow completed. Check the output folder for CSV and anonymized DICOMs.")
