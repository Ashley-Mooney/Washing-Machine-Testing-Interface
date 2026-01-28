
What This Is
Source code for testing your interpreter implementation. These tests will actually test your code when compiled together.

Quick Start
1. Get the Files
Copy all these files into your project folder (same place as your memory.c, parser.c, etc.):

text
tests_memory.c
tests_parser.c
tests_executor.c
tests_integration.c
test_runner.c
executor_basic.txt
executor_incdec.txt
executor_arith.txt
executor_andxor.txt
parser_test1.txt
integration_basic.txt
integration_print.txt
How to Test Me.txt
2. Compile the Tests
Run these commands in your project folder:

bash
# Memory tests
gcc -o tests_memory tests_memory.c memory.c errors.c

# Parser tests
gcc -o tests_parser tests_parser.c parser.c

# Executor tests
gcc -o tests_executor tests_executor.c memory.c parser.c executor.c errors.c

# Integration tests
gcc -o tests_integration tests_integration.c memory.c parser.c executor.c errors.c

# Test runner (main menu)
gcc -o test_runner test_runner.c
3. Run the Tests
bash
./test_runner
What Gets Tested
Memory Tests (tests_memory)
Tests your memory.c implementation:

Creating variables with var_allocate()

Reading/writing values with var_read_at()/var_write_at()

Freeing memory with var_free()

Checking if variables exist

Parser Tests (tests_parser)
Tests your parser.c implementation:

Reading commands from .txt files

Recognizing Mal, Ass, Add, Sub, etc.

Extracting variable names and numbers

Executor Tests (tests_executor)
Tests your executor.c implementation:

Actually running commands

Arithmetic operations (Add, Sub, Mul)

Bitwise operations (And, Xor)

Increment/Decrement (Inc, Dec)

Integration Tests (tests_integration)
Tests everything together:

Complete programs end-to-end

Multiple commands in sequence

Memory cleanup

How It Works
When you compile tests_memory.c with your memory.c:

The test code calls YOUR var_allocate(), var_get(), etc.

It checks if YOUR implementation works correctly

Same for all other test files

Using the Test Runner
Run ./test_runner for a menu:

text
MAIN MENU
1. Run ALL tests
2. Run MEMORY tests only
3. Run PARSER tests only
4. Run EXECUTOR tests only
5. Run INTEGRATION tests only
6. Show what each test does
7. Get help
8. Exit
Testing Your Code
Before Making Changes:
bash
./test_runner
# Choose option 1 to run all tests
# Make sure everything passes
After Making Changes:
bash
# Run tests again
./test_runner
# Fix any failing tests
If a Test Fails:
Read the error message

Look at which test file failed

Check your implementation of that function

Fix the bug

Run tests again

File Requirements
Your project must have these files:

memory.c and memory.h

parser.c and parser.h

executor.c and executor.h

errors.c and errors.h

All .txt test files must be in the same folder as the compiled programs.

Common Issues
"File not found" error
Make sure all .txt files are in the same folder as your compiled .exe files.

Compilation errors
Check that:

All .c and .h files are in the same folder

Your function names match what the tests expect

You're not missing any required files

Tests pass but interpreter doesn't work
The tests check specific cases. Your interpreter might have bugs in cases not covered by tests.

Adding New Tests
Add test code to the appropriate .c file

Create new .txt test files if needed

Recompile and run tests

For Windows Users
Use .exe extension:

bash
gcc -o tests_memory.exe tests_memory.c memory.c errors.c
# etc...
test_runner.exe
For Linux/Mac Users
Make sure files are executable:

bash
chmod +x test_runner tests_memory tests_parser tests_executor tests_integration
Understanding Test Output
Exit code 0: All tests passed

Exit code 1: Some tests failed

Error messages show what went wrong

Each assert() that fails gives details

Workflow
Start: Run all tests (./test_runner → option 1)

Make changes to your interpreter

Test: Run tests again

Fix: Any failing tests

Repeat until all tests pass

Need More Help?
Read How to Test Me.txt for detailed testing methodology.

Summary
Copy test files to your project

Compile tests with your code

Run ./test_runner

Fix any failing tests

Your interpreter should now work correctly
