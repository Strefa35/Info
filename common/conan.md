
# Install
    pip install conan

    pip install conan --upgrade
    
# Commands
    https://docs.conan.io/en/latest/reference/commands.html
    
    ## Installs the requirements specified in a recipe (conanfile.py or conanfile.txt).
        conan install . --profile profiles/my-profile --install-folder=tmp/config
        
    ## Builds a binary package for a recipe (conanfile.py).    
        conan create . --source-folder=tmp/source --build-folder=tmp/build
        
    ## Calls your local conanfile.py ‘build()’ method.
        conan build . --source-folder=tmp/source --build-folder=tmp/build
        
# Remotes
    https://docs.conan.io/en/latest/uploading_packages/remotes.html
    
    conan remote add conan-center https://conan.bintray.com
    conan remote add bincrafters https://api.bintray.com/conan/bincrafters/public-conan
    conan remote add conan-community https://api.bintray.com/conan/conan-community/conan
    
    conan remote list
    
# Developing packages
    https://docs.conan.io/en/latest/developing_packages.html
    
    ## Package development flow
        https://docs.conan.io/en/latest/developing_packages/package_dev_flow.html
    
# conanfile.txt
    https://docs.conan.io/en/latest/reference/conanfile_txt.html
    
# conanfile.py
    https://docs.conan.io/en/latest/reference/conanfile.html

# Generators
    https://docs.conan.io/en/latest/reference/generators.html

