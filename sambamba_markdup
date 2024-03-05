#!/bin/bash

# Input parameters
bam_files="*.sorted.bam"

# Loop through all BAM files
for bam_file in $bam_files; do
    # Check if the file exists
    if [ -e "$bam_file" ]; then
        # Extract base name without extension
        base_name=$(basename "$bam_file" .sorted.bam)

        # Mark duplicates and redirect errors to a text file
        sambamba markdup "$bam_file" "${base_name}_markdup.bam" 2> "${base_name}_markdup.txt"

        echo "Marked duplicates for: ${base_name}"
    else
        echo "File not found: ${bam_file}"
    fi
done

echo "Marking duplicates completed."
