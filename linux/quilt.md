# Install quilt tool
  sudo apt-get install quilt

## Tutorial
  http://www.shakthimaan.com/downloads/glv/quilt-tutorial/quilt-doc.pdf

## Prepare some setup for quilt to use our patches
  Run below script:
```
#!/bin/bash
PATCH_FILES=*.patch
SERIES_FILE="series"
for f in ${PATCH_FILES}
do
  echo "Add $f file to ${SERIES_FILE}..."
  echo ${f} >> ${SERIES_FILE}
done
echo -e "DONE.\n"
```
## Now you can start patching...
1. ```quilt series``` - shows list of patches from series file
2. ```quilt push``` - do as many times as there are patch files
3. ```quilt applied``` - shows you which patch files was patched

## Navigate
- ```quilt new new-file-name``` - create a new patch
- ```quilt add new-file-name``` - add one or more files to the patch
- ```quilt pop``` - back one patch on the list
- ```quilt push``` - apply patch(es) from the series file.
- ```quilt applied``` - a list of applied patches
- ```quilt refresh``` - update a patch with changes
