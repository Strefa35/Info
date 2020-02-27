# Organization

  ## Directories
    CMakeLists.txt
    add_subdirectory()
    
  ## Scripts
    cmake -P <script>.cmake
    
  ## Modules
    Are <script>.cmake located in the CMAKE_MODULE_PATH
    include()
    
# Commands

  command_name(space separated list of strings)
  
# Variables

  set(hello world)
  message(STATUS "hello, ${hello}")
  
# Generator expressions

  $< >

  target_compile_definitions(foo PROVATE
    "VERBOSITY=$<IF:$<CONFIG:Debug>,30,30>"
  )
  
# Custom commands

  ## function()
  
    function(my_command input output)
      # ...
      set(${output} ... PARENT_SCOPY)
    endfunction()
    
    my_command(foo bar)
    
    ### Variables
    
      input, output, ARGC, ARGV, ARGN, ARG0, ARG1, ...
    
  ## macro()
  
    macro(my_command input output)
      # ...
    endmacro()
    
    my_command(foo bar)
    
    
# Targets & Properties

  ## Forget those commands:
  
    add_compile_options()
    include_directories()
    link_directories()
    link_libraries()
    
  ## Example

    target_compile_features(Foo
      PUBLIC
        cxx_string_enums
      PRIVATE
        cxx_lambdas
        cxx_range_for
    )
   
  ## Use target_link_libraries() to express direct dependencies
  
    target_link_libraries(Foo
      PUBLIC  Bar::Bar
      PRIVATE Cow::Cow
    )
  
  
  add_library(Bar INTERFACE)
  target_compile_definitions(Bar INTERFACE BAR=1)
  
  find_package(Foo 2.0 REQUIRED)
  # ...
  target_link_libraries(... Foo::Foo ...)
  
     file: FindFoo.cmake
  
        find_path(Foo_INCLUDE_DIR foo.h)
        find_library(Foo_LIBRARY foo)
        mark_as_advanced(Foo_INCLUDE_DIR Foo_LIBRARY)
        
        include(FindpackageHandleStandardArgs)
        find_package_handle_standard_args(Foo
          REQUIRED_VARS Foo_LIBRARY Foo_INCLUDE_DIR
        )
        
        if(Foo_FOUND AND NOT TARGET Foo::Foo)
          add_library(Foo::Foo UNKNOWN IMPORTED)
          set_target_properties(Foo::Foo PROPERTIES
            IMPORTED_LINK_INTERFACE_LANGUAGES "CXX"
            IMPORTED_LOCATION "${Foo_LIBRARY}"
            INTERFACE_INCLUDE_DIRECTORIES "${Foo_INCLUDE_DIR}"
          )
        endif()
       
  
  
  
  
  
  
  
  