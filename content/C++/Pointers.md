[[C++]]
## Pointer Arithmetic

Incrementing a pointer...

```C++

```

## Array decay

An array used in an expression will decay to (become) a pointer to the first element. Still, an array is more than just a pointer: if we run `sizeof(array)` it wont just give the memory size of the first element, but of the entire array.
### Passing arrays to a function

When an array is passed inside a function, array decay happens.

```C++
void print_array(double arr[], size_t size)
{
	// arr is now a pointer
	for (size_t i = 0; i < size; i++)
	{
		std::cout << arr + i << std::endl;     // memory addresses
		std::cout << *(arr + 1) << std::endl;  // variables
	}
}

void print_array(double arr[]);
void print_array(double* arr);  // not using [] -> array decay
```
## Heap Memory

```C++
int* intHeap = new int;
delete intHeap;

int* arrHeap = new int[size];  // no need to know size at compilation time
delete[] arrHeap;
```