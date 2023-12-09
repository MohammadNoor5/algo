# algo
#include <iostream>
#include <chrono>
using namespace std;
using namespace std::chrono;
long long iterativeFactorial(int n) {
long long result = 1 ;
for (int i = 1; i <= n; ++i) {
result *= i ;
}
return result
}
long long recursiveFactorial(int n){
if (n == 0 || n == 1){
return 1 ;
}
else }
return n * recursiveFactorial(n - 1);
}
}
void testFactorial(long long (*factorialFunction)(int), int n){
auto start = high_resolution_clock::now();
long long result = factorialFunction(n);
auto stop = high_resolution_clock::now();
auto duration = duration_cast<milliseconds>(stop - start);
cout << "Execution time for input " << n << ": " << duration.count() << " milliseconds" << endl;
}
int main(){
 int valueToTest;
cin>>valueToTest;
cout << "Testing Iterative Factorial:" << endl;
testFactorial(iterativeFactorial, valueToTest);
cout << "\nTesting Recursive Factorial:" << endl;
testFactorial(recursiveFactorial, valueToTest);
return 0; }
