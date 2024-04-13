# <a name="title"></a> Developers Guide

## Code style

1. **Cpp**: Follow the [ROS Cpp Style Guide](http://wiki.ros.org/CppStyleGuide) rigorously.
2. **CMake**: Follow [Caktin CMake Style Guide](https://cmake.org/cmake/help/latest/manual/cmake-style.7.html).
3. **Python**: Code should follow PEP8. Please see [ROS PyStyleGuide](https://wiki.ros.org/PyStyleGuide) for details. Use Anaconda plugin for Sublime Text editor for style check.
4. **Bash**: Use the provided python script.
5. **Roslint**: All packages (except commons packages which don't have C++ or Python code) depend on roslint for static code analysis.

Note: Utils contains scripts for formatting C++, Python, XML, CMakeLists files. Since these are bash scripts, there is a formatting script for Bash.
<!-- 
# <a name="title"></a> Developers Guide -->

## Documentation

We maintain several forms of online documentation for ROS packages:

- **MKD DOCS**: This is the DOCUMENTATION repo. Home for tutorials, design documents, technical details, research and other sorts of information. This is mainly for people running our code. In general, anything that people need to know outside source, to run the AUV software/ hardware successfully.
- **Auto-generated code documentation Internal docs**: This is mainly for people integrating with or editing your code. These are auto-generated from source code comments using Doxygen. Travis CI generated and auto-deploys to the gh-pages branch. Located at [AUV documentation](http://auv-iitk.github.io/auv/). Look at sample commit to see how to add documentation. Also, the Doxygen manual is good for a quick start.

## Source control

- We use Git. Read the wiki page on git.

## Bug tracking

- We use GitHub issues on AUV repo for tracking bugs.

## Testing

We use two levels of testing:

1. **Library**: At the library level, we use standard unit-test frameworks. In C++, we use gtest. In Python, we use unittest.
2. **Message**: At the message level, we use rostest to set up a system of ROS nodes, run a test node, then tear down the system.
   ROS has established best practices and policies for writing and running tests.
   AUV code is structured in layers, with each layer interacting with the other using actionlib. For testing each layer separately, we use unit tests nodes which are part of the concerning layer itself.

## Standardization

- Code should use ROS services, follow guidelines for their use:
  - Use rosout for printing messages.
  - Use the ROS Clock for time-based routines.

## Large data files

- Large files (anything over 1MB, really) often don't belong in the AUV repositories, especially if they are just used for tests. These large files affect the time that it takes to checkout the repository.

## Naming Convention

- Please refer to ROS CppStyleGuide and ROS Conventions.
- Avoid using any sort of Hungarian notation on names and "_ptr" on pointers.

| Code Element     | Style                | Comment                                                  |
|------------------|----------------------|----------------------------------------------------------|
| Namespace        | under_scored         | Differentiate from class names                           |
| Class name       | CamelCase            | To differentiate from STL types which ISO recommends     |
| Function name    | camelCase            | Lower case start is almost universal                     |
| Parameters/Locals| under_scored         | Vast majority of standards recommends this                |
| Member variables | under_scored_with_   | The prefix _ is heavily discouraged                      |
| Enums and members| CamelCase            | Most except very old standards agree                      |
| Globals          | g_under_scored       | You shouldn't have these in first place!                  |
| Constants        | UPPER_CASE           | Very contentious and we just have to pick one here        |
| File names       | Match case of class name in file | This removes inconsistency in auto-generated code |

### Header Files

- Use a namespace qualified #ifdef to protect against multiple inclusion:
 ```cpp

    // ifndef msr_airsim_MyHeader_hpp


    // #define msr_airsim_MyHeader_hpp


    // #endif
