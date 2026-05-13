# Quilt

## Install

```bash
sudo apt-get install quilt
```

## Tutorial

<http://www.shakthimaan.com/downloads/glv/quilt-tutorial/quilt-doc.pdf>

## Prepare patch series

Run this script to populate the `series` file from all `*.patch` files in the current directory:

```bash
#!/bin/bash
PATCH_FILES=*.patch
SERIES_FILE="series"
for f in ${PATCH_FILES}; do
  echo "Add $f file to ${SERIES_FILE}..."
  echo ${f} >> ${SERIES_FILE}
done
echo -e "DONE.\n"
```

## Apply patches

```bash
quilt series     # show list of patches from series file
quilt push       # apply next patch (repeat for each patch file)
quilt applied    # show which patches have been applied
```

## Navigate patches

```bash
quilt new new-file-name    # create a new patch
quilt add new-file-name    # add one or more files to the patch
quilt pop                  # go back one patch
quilt push                 # apply next patch from series file
quilt applied              # list applied patches
quilt refresh              # update current patch with changes
```
