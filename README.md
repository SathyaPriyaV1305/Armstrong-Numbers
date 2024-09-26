// C Program to Demonstrate
// Armstrong numbers between
// two integers
#include <math.h>
#include <stdio.h>

int power(int x, unsigned int y)
{
	// Initialize result
	int res = 1;

	while (y > 0) {
		// If y is odd, multiply
		// x with result
		if (y & 1)
			res = res * x;

		// y must be even now
		y = y >> 1; // y = y/2
		x = x * x; // Change x to x^2
	}
	return res;
}

int main()
{
	int lowerlimit, higherlimit;
	printf("Enter lowerlimit and Higher limit:\n ");
	scanf("%d%d", &lowerlimit, &higherlimit);

	for (int i = lowerlimit + 1; i < higherlimit; ++i) {
		int x = i;
		int n = 0;
	
		// number of digits calculation
		while (x != 0) {
			x /= 10;
			++n;
		}
		int powersum = 0;
		x = i;
		// finding the sum of n
		// th power of its digits
		while (x != 0) {
			int digit = x % 10;
			powersum += power(digit, n);
			x /= 10;
		}
		// checking if the obtained
		// number is armstrong or
		// not
		if (powersum == i)

			// printing the result
			printf("%d ", i);
	}
	printf("\n");
	return 0;
}
# Armstrong-Numbers
