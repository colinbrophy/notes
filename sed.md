Interpreting this as: run sed on all files within subdirectories. Below are the standard, correct patterns depending on intent.

find . -type f -exec sed -i 's/OLD/NEW/g' {} +
