# Install quilt tool
  sudo apt-get install quilt

## Tutorial
  http://www.shakthimaan.com/downloads/glv/quilt-tutorial/quilt-doc.pdf

## Prepare some setup for quilt to use our patches
  Run below script:

    #!/bin/bash
    PATCH_FILES=*.patch
    SERIES_FILE="series"
    for f in ${PATCH_FILES}
    do
      echo "Add $f file to ${SERIES_FILE}..."
      echo ${f} >> ${SERIES_FILE}
    done
    echo -e "DONE.\n"
 
## Now you can start patching...
  1. quilt series - shows list of patches from series file
  2. make: quilt push
      do as many times as there are patch files
  3. quilt applied shows you which patch files was patched
 
## Navigate 
  quilt pop
  quilt push

## Example
  /* back one patch on the list */
  quilt pop

  /* add some changes to the same files as patch file has */ or
  /* add a new files to this patch */ -> quilt add new-file-name
  /* modify new-file-name */

  /* refresh all changes, all a new files */
  quilt refresh
