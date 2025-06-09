#flashcards
What is the purpose of binary search?::to find the position of a target element in a sorted array in logarithmic time

What must be true about the input array for binary search to work correctly?::the array must be sorted in non-decreasing order

What is the base case in recursive binary search?::when the search interval is empty, i.e., low > high, return -1 to indicate target not found

How do you calculate the middle index in binary search?::mid = (low + high) // 2
<!--SR:!2025-06-13,4,270-->

What is the time complexity of binary search on an array of size n?::O(log n)

What is the space complexity of recursive binary search?::O(log n) due to the recursion call stack
<!--SR:!2025-06-13,4,270-->

How does binary search decide which half of the array to search next?::if arr[mid] > target, search left half; if arr[mid] < target, search right half; else return mid

What value does binary search return if the target is not found?::-1

What is the difference between iterative and recursive binary search in terms of space complexity?::iterative uses O(1) space; recursive uses O(log n) space

Can binary search be applied to unsorted arrays?::no, it requires a sorted array to work correctly

What happens if you compute mid as (low + high) // 2 in languages with fixed integer size and very large low and high?::possible integer overflow, safer formula is low + (high - low) // 2

How would you modify binary search to find the first occurrence of a target in an array with duplicates?::on arr[mid] == target, recurse or iterate on left half to find earlier occurrence

What does binary search return if the array is empty?::-1, since low > high immediately

Why is binary search considered efficient compared to linear search?::it reduces search space by half each step, achieving O(log n) vs O(n) time

Can binary search be used to find an element in a linked list?::no, because random access to mid element is not O(1)

Explain why binary search requires a total order relation on array elements.::because it relies on consistent comparisons to decide direction, partial or inconsistent orders break the logic
<!--SR:!2025-06-12,3,250-->

What’s the worst-case number of recursive calls for binary search on an array of size n?::⌊log₂(n)⌋ + 1

If binary search is called with invalid bounds, e.g., low > high, what happens?::immediate termination with -1 indicating not found

Why is tail recursion optimization relevant to recursive binary search?::it can reduce stack usage, but python doesn’t optimize tail calls so recursion depth remains O(log n)
<!--SR:!2025-06-13,4,270-->

What is the recurrence relation that describes the running time of recursive binary search?::T(n) = T(n/2) + O(1)

How do you handle searching for a target in a descending sorted array using binary search?::adjust comparison logic to reverse: if arr[mid] < target, search left; else right

What is the effect of floating point imprecision when searching for a floating target?::can cause missed matches; must use epsilon threshold to approximate equality

Why might recursive binary search be less preferred than iterative in production code?::due to recursion overhead and risk of stack overflow

If the array contains multiple occurrences of the target, what index does binary search return?::any one occurrence, not guaranteed to be first or last

What is the significance of the mid calculation method in preventing bugs?::using (low + high)//2 is simple but can overflow in fixed-width int; safer to use low + (high - low)//2

What is the behavior of binary search when the target is smaller than all elements?::returns -1 after checking all halves

What is the time complexity of searching in an unsorted array?::O(n) with linear search; binary search is invalid

How would you prove correctness of binary search?::by induction on the size of the search interval showing the target must lie within the chosen half if it exists

If the target value is found at mid, what happens next in recursive binary search?::the index mid is returned immediately, terminating recursion

Why does binary search only work on data structures that support random access?::because mid element must be accessed in O(1) time for O(log n) performance

What is the practical consequence of integer overflow in mid calculation in C or Java?::incorrect mid leading to infinite loops or incorrect results

If the array has one element, how does binary search behave?::checks the single element, returns 0 if matches, else -1

What would cause binary search to return -1 incorrectly?::unsorted input, broken comparison, invalid indices, or searching for missing target