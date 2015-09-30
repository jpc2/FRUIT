Test Programs
-------------

Test program files should be named module_test.f90.

The module tests should have names in the form 'test_module_shoud_do_something'.

Subroutines can be provided to setup and tear down necessary context for the tests. Do not include parentheses on the name or FRUIT will not see them. The subroutines '**setup**' and '**teardown**' are called before and after each test subroutine. The subroutines '**setup_before_all**' and '**teardown_after_all**' are called once before and after the suite of tests is run.

Asserts provided in fruit.f90
---------

```fortran
  assert_true(var1, fail_msg)
  assert_false(var1, fail_msg)
  assert_equals and assert_not_equals
    !supported versions
    logical                     - (var1, var2, fail_msg)
    logical 1d arrays           - (var1, var2, n, fail_msg)
    logical 2d arrays           - (var1, var2, n, m, fail_msg)
    string                      - (var1, var2, fail_msg)
    string  1d arrays           - (var1, var2, n, fail_msg)
    string  2d arrays           - (var1, var2, n, m, fail_msg)
    integer                     - (var1, var2, fail_msg)
    integer 1d arrays           - (var1, var2, n, fail_msg)
    integer 2d arrays           - (var1, var2, n, m, fail_msg)
    real                        - (var1, var2, fail_msg)
    real in range               - (var1, var2, delta, fail_msg)
    real 1d arrays              - (var1, var2, n, fail_msg)
    real 1d arrays in range     - (var1, var2, n, delta, fail_msg)
    real 2d arrays              - (var1, var2, n, m, fail_msg)
    real 2d arrays in range     - (var1, var2, n, m, delta, fail_msg)
    double                      - (var1, var2, fail_msg)
    double in range             - (var1, var2, delta, fail_msg)
    double 1d arrays            - (var1, var2, n, fail_msg)
    double 1d arrays in range   - (var1, var2, n, delta, fail_msg)
    double 2d arrays            - (var1, var2, n, m, fail_msg)
    double 2d arrays in range   - (var1, var2, n, m, delta, fail_msg)
    complex                     - (var1, var2, fail_msg)
    complex in range            - (var1, var2, delta, fail_msg)
    complex 1d arrays           - (var1, var2, n, fail_msg)
    complex 1d arrays in range  - (var1, var2, n, delta, fail_msg)
    complex 2d arrays           - (var1, var2, n, m, fail_msg)
    complex 2d arrays in range  - (var1, var2, n, m, delta, fail_msg)

```

Useful routines available in fruit_util.f90
-----------------

The following routines might be of use.

```fortran
  equals
    !Compares two variables, returns .TRUE. or .FALSE.
    !Supported versions
      real with tolerance   - (var1, var2, epsilon)
      real with tol= 1E-6   - (var1, var2)
      integer               - (var1, var2)
      double with tol=1E-6  - (var1, var2)
      string                - (var1, var2)
      logical               - (var1, var2)

  to_s(var)
    !Returns a left justified string for var. 
    !Equavalent to 'write(str,*).
    !supports:
      integer
      real
      logical
      double
      complex
      string

  strip(var)
    !Returns the characters in var striped of leading and trailing blanks.

  strip_length(var,length)
    !Returns the characters in var striped of leading and trailing blanks.
    !The the length of the resulting string is returned in 'length'.
```
