# file-organizer-project-1-
import os
This imports the os module, which provides functions for interacting with the operating system, such as file and directory management.

def organize_files(directory):
This defines a function named organize_files that takes a single parameter, directory, representing the path to the directory to be organized.

if not os.path.exists(directory):
Checks if the provided directory exists. If not, it prints an error message and exits the function.

for file in os.listdir(directory):
Iterates over all files and directories in the specified directory using os.listdir().

file_path = os.path.join(directory, file)
Constructs the full path to the file by joining the directory path and the file name.

if os.path.isfile(file_path):
Checks if the current item is a file (and not a directory).

ext = file.split('.')[-1]
Extracts the file extension by splitting the file name at periods and taking the last part (e.g., file.txt -> txt).

ext_folder = os.path.join(directory, ext)
Constructs the path to the subdirectory where files with the current extension should be placed.

if not os.path.exists(ext_folder):
Checks if the subdirectory for the extension already exists. If not, it creates it using os.mkdir(ext_folder).

os.rename(file_path, os.path.join(ext_folder, file))
Moves the file into the corresponding subdirectory by renaming it with the new path.

print("Files have been organized by extension.")
Prints a success message after organizing the files.

