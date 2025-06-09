from zipfile import ZipFile
import os


zip_path = "ilhan-generation-website.zip"
extract_path = "ilhan-generation-files"
with ZipFile(zip_path, 'r') as zip_ref:
    zip_ref.extractall()
print("Files extracted:", os.listdir(extract_path))
# ilhan-generation
