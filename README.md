# EigenNet
A .NET wrapper for the Eigen math library.

This project contains four components, some of which implement the same functions in different ways:

* **NativeEigenWrapper** - A DLL that contains compiled Eigen matrix library functions for use by other programs (primarily, the EigenWrapper DLL).
* **EigenWrapper** - A .NET wrapper which calls NativeEigenWrapper using P/Invoke calls.  This was found to be faster than using C++/CLI in testing.
* **EigenWrapper_CppCLI** - A .NET wrapper for the Eigen matrix library using C++/CLI.  As this code was found to be slower than the P/Invoke method, fewer functions have been implemented in EigenWrapper_CppCLI than in EigenWrapper.
* **WrapperTest** - A simple test code spot check the correctness and speed of different wrapper implementations.  The testing is not exaustive.  Also contains a matrix math class implemented completely in C# (and thus does not have access to SIMD instructions).

**Note:** Matrix operations using the Eigen library are significantly slower in debug mode than in release mode.

## Requirements:

* [Microsoft .NET Framework](https://www.microsoft.com/en-us/download/details.aspx?id=17851) (currently tested against 4.0)
* [Eigen](http://eigen.tuxfamily.org/index.php?title=Main_Page) (currently tested against 3.2.0)
