# TODO1: Add an executable target for the tests
add_executable(math_test)

# TODO2: Add the TestMathFunctions.cxx file to the test target's sources
target_sources(math_test PRIVATE TestMathFunctions.cxx)

# TODO3: Add the MathFunctions library to the test target's link libraries
target_link_libraries(math_test PRIVATE MathFunctions)

# TODO4: Write a function that takes a single operation name as an argument. The
# function will call add_test() with the operation name as the NAME of the test,
# and a COMMAND of the form: <TestTarget> <operation name>
function(add_math_test operation)
  add_test(NAME ${operation} COMMAND math_test ${operation})
endfunction()

# TODO5: Call the function for all four supported operations: add, mul, sqrt,
# sub
add_math_test(add)
add_math_test(mul)
add_math_test(sqrt)
add_math_test(sub)