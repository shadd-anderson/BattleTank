cmake_minimum_required (VERSION 2.6)
project (UE4)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_COMPILER "C:/MinGW/bin/g++.exe")
set(CMAKE_C_COMPILER "C:/MinGW/bin/gcc.exe")

include("C:/Users/shadd/Unreal-Projects/Section_04/BattleTank/BattleTank/Intermediate/ProjectFiles/IncludeDirectories.cmake")
include("C:/Users/shadd/Unreal-Projects/Section_04/BattleTank/BattleTank/Intermediate/ProjectFiles/Definitions.cmake")
include("C:/Users/shadd/Unreal-Projects/Section_04/BattleTank/BattleTank/Intermediate/ProjectFiles/BattleTank.cmake")

set(MONO_ROOT_PATH "C:/UnrealEngine-release/Engine/Binaries/DotNET")
set(BUILD cd "${MONO_ROOT_PATH}")

# Custom target for BattleTank project, Development configuration
add_custom_target(BattleTank-Development ${BUILD} && UnrealBuildTool.exe BattleTank Win64 Development -project="C:/Users/shadd/Unreal-Projects/Section_04/BattleTank/BattleTank/BattleTank.uproject" -game)
add_custom_target(BattleTank-Development-CLEAN ${BUILD} && UnrealBuildTool.exe BattleTank Win64 Development -project="C:/Users/shadd/Unreal-Projects/Section_04/BattleTank/BattleTank/BattleTank.uproject" -clean)

include("C:/Users/shadd/Unreal-Projects/Section_04/BattleTank/BattleTank/Intermediate/ProjectFiles/BattleTankEditor.cmake")

# Custom target for BattleTankEditor project, Development configuration
add_custom_target(BattleTankEditor-Development ${BUILD} && UnrealBuildTool.exe BattleTankEditor Win64 Development -project="C:/Users/shadd/Unreal-Projects/Section_04/BattleTank/BattleTank/BattleTank.uproject" -game)
add_custom_target(BattleTankEditor-Development-CLEAN ${BUILD} && UnrealBuildTool.exe BattleTankEditor Win64 Development -project="C:/Users/shadd/Unreal-Projects/Section_04/BattleTank/BattleTank/BattleTank.uproject" -clean)

add_executable(PleaseIgnoreMe ${BattleTankEditor_FILES})