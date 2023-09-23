# Codewars_Python_tests
<P1>Tests for python codewars solution

	import unittest
	from solution import factorial

#Standard output

	class CustomTextTestResult(unittest.TextTestResult):
	    def addSuccess(self, test):
		super().addSuccess(test)
		test_name = test._testMethodName.replace('test_', 'Test ')
		self.stream.writeln(f'{test_name}: Passed')
	
	    def addFailure(self, test, err):
		super().addFailure(test, err)
		test_name = test._testMethodName.replace('test_', 'Test ')
		self.stream.writeln(f'{test_name}: Failed')

#Actual tests

	class Tests(unittest.TestCase):
	    def test_1(self):
		self.assertEqual(factorial(0), 1)
	
	    def test_2(self):
		self.assertEqual(factorial(1), 1)
	
	    def test_3(self):
		self.assertEqual(factorial(2), 2)
	
	    def test_4(self):
		self.assertEqual(factorial(3), 6)
	
	    def test_5(self):
		self.assertEqual(factorial(4), 24)
	    
	    def test_6(self):
		self.assertEqual(factorial(5), 120)
	
	    def test_7(self):
		self.assertEqual(factorial(6), 720)
	
	    def test_8(self):
		self.assertEqual(factorial(7), 5040)    
	
	if __name__ == '__main__':
	    unittest.main(testRunner=unittest.TextTestRunner(resultclass=CustomTextTestResult))
