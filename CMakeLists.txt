cmake_minimum_required(VERSION 3.14)
project(S20-PA01-SentimentAnalysis)
set (EXE_NAME SentimentAnalyzer)

##########################################
# Students, edit the items below.  In the quotes,
# put the names of the input files as they should appear
# in the argv param to main.
# Example:
#   set (input01 "train_data.csv")
#   set (input02 "train_target.csv")
# etc....

set (input01 "stop-word-list.txt")
set (input02 "dev-train-data.csv")
set (input03 "dev-train-target.csv")
set (input04 "dev-test-data.csv")
set (input05 "dev-test-target.csv")



##########################################

# Copy data files to build dir
foreach(file IN LISTS input01 input02 input03 input04 input05)           # Modify this too
    configure_file(${file} ${file} COPYONLY)
endforeach()

set(CMAKE_CXX_STANDARD 17)
add_executable(${EXE_NAME} main.cpp DSString.cpp DSString.h test.cpp)    # Modify this too
