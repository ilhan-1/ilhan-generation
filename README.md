from zipfile import ZipFile
import os

# Path to your ZIP file
zip_path = "ilhan-generation-website.zip"
extract_path = "ilhan-generation-files"

# Extract ZIP
with ZipFile(zip_path, 'r') as zip_ref:
    zip_ref.extractall(extract_path)

# List extracted files
print("Files extracted:", os.listdir(extract_path))
