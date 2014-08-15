get_repeat
==========

get repeat in a array

#include <iostream>
using namespace std;

const int ARRAY_LEN = 10011;
const int REPEATE = 333;

void produce_array(int* array, int n, int repeat) 
{
	int i = 0;
	for (; i < n; i ++)
      array[i] = i + 1;	
 
    array[n] = repeat;
}

int get_repeat(int *array, int len)
{
	int i = 0;
	int res = 0;
	
	for (; i < len; i ++)
	  res ^= array[i];  
	  
    i = len - (len - 4) & 3;
    
	for (; i < len; i ++)
      res ^= i;
 
    return res;
}

int main() {
	int res = 0;
	int array[ARRAY_LEN + 1];
	
	produce_array(array, ARRAY_LEN, REPEATE);
	  
	res = get_repeat(array, ARRAY_LEN + 1);
 
     cout << res << endl;
}
