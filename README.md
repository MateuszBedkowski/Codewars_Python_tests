# Codewars_Python_tests
<P1>Tests for python codewars solution

import unittest
from solution import dodawanie

#Standard output
----------------------------------------------------
class CustomTextTestResult(unittest.TextTestResult):
    def addSuccess(self, test):
        super().addSuccess(test)
        test_name = test._testMethodName.replace('test_', '')
        self.stream.writeln(f'Test {test_name}: Passed')

    def addFailure(self, test, err):
        super().addFailure(test, err)
        test_name = test._testMethodName.replace('test_', '')
        self.stream.writeln(f'Test {test_name}: Failed')

#Actual tests
---------------------------------------------
class TestYourCode(unittest.TestCase):
    def test_dodawanie_2_plus_3(self):
        self.assertEqual(dodawanie(2, 3), 5)

    def test_dodawanie_0_plus_7(self):
        self.assertEqual(dodawanie(0, 7), 7)

    def test_dodawanie_21_minus_3(self):
        self.assertEqual(dodawanie(21, -3), 18)

    def test_dodawanie_12_plus_38(self):
        self.assertEqual(dodawanie(12, 38), 50)

    def test_dodawanie_99_plus_1(self):
        self.assertEqual(dodawanie(99, 1), 100)

if __name__ == '__main__':
    unittest.main(testRunner=unittest.TextTestRunner(resultclass=CustomTextTestResult))
