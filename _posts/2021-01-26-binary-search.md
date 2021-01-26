---
layout: post
---

binary search
-------------
binary search is a "divide and conquer" algorithm. the searched key is compeared with the key in the middle of de orderedlist, if not equal, the upper or lower half of the list is searched.

item for seach: 64

|                     |                        |
| ------------------- | :--------------------: |
| indicies of array   | 0 1 2 3 4 5 6  7  8  9 |
| values in the array | 1 3 5 9 22 34 64 77 93 |

<hr>

binary search function 
```c++

#include <iostream>
using namespace std;

int binarySearch(int list[], int length, int item)
{
	int low = 0, high = length - 1, mid;

	while (low <= high)
	{
		mid = (low + high) / 2;
		if (item == list[mid])
		{
			return mid;
		}
		else if (item < list[mid])
		{
			high = mid - 1;
		}
		else
		{
			low = mid + 1;
		}
	}
	return -1;
}

int main()
{
	int list[] = {1, 3, 5, 9, 22, 34, 64, 77, 93};
	int pos = binarySearch(list, 9, 22);
	if (pos >= 0)
	{
		cout << "Item found in position " << pos << endl;
	}
	else
	{
		cout << "404 not found" << endl;
	}
}

```