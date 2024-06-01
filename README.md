def gcd_division(a, b):
    while b != 0:
        remainder = a % b
        print(f"{a} = {a//b} * {b} + {remainder}")
        a = b
        b = remainder
    return a

a = 120
b = 25
print("The Euclidean algorithm using division:\n")
print(f"The GCD of {a} and {b} is: {gcd_division(a, b)}")
def gcd_subtraction(a, b):
    while a != b:
        if a > b:
            print(f"{a} - {b} = {a-b}")
            a = a - b
        else:
            print(f"{b} - {a} = {b-a}")
            b = b - a
    return a

a = 120
b = 25
print("The Euclidean algorithm using subtraction:\n")
print(f"The GCD of {a} and {b} is: {gcd_subtraction(a, b)}")
def knapsack_brute_force(capacity, n):
    print(f"knapsack_brute_force({capacity},{n})")
    if n == 0 or capacity == 0:
        return 0

    elif weights[n-1] > capacity:
        return knapsack_brute_force(capacity, n-1)

    else:
        include_item = values[n-1] + knapsack_brute_force(capacity-weights[n-1], n-1)
        exclude_item = knapsack_brute_force(capacity, n-1)
        return max(include_item, exclude_item)

values = [300, 200, 400, 500]
weights = [2, 1, 5, 3]
capacity = 10
n = len(values)

print("\nMaximum value in Knapsack =", knapsack_brute_force(capacity, n))
def fibonacci_tabulation(n):
    if n == 0: return 0
    elif n == 1: return 1

    F = [0] * (n + 1)
    F[0] = 0 
    F[1] = 1

    for i in range(2, n + 1):
        F[i] = F[i - 1] + F[i - 2]
    
    print(F)
    return F[n]
  
n = 10
result = fibonacci_tabulation(n)
print(f"\nThe {n}th Fibonacci number is {result}")
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

def findLowestValue(head):
    minValue = head.data
    currentNode = head.next
    while currentNode:
        if currentNode.data < minValue:
            minValue = currentNode.data
        currentNode = currentNode.next
    return minValue

node1 = Node(7)
node2 = Node(11)
node3 = Node(3)
node4 = Node(2)
node5 = Node(9)

node1.next = node2
node2.next = node3
node3.next = node4
node4.next = node5

print("The lowest value in the linked list is:", findLowestValue(node1))
def binarySearch(arr, targetVal):
    left = 0
    right = len(arr) - 1

    while left <= right:
        mid = (left + right) // 2

        if arr[mid] == targetVal:
            return mid
        
        if arr[mid] < targetVal:
            left = mid + 1
        else:
            right = mid - 1

    return -1

myArray = [1, 3, 5, 7, 9, 11, 13, 15, 17, 19]
myTarget = 15

result = binarySearch(myArray, myTarget)

if result != -1:
    print("Value",myTarget,"found at index", result)
else:
    print("Target not found in array.")
def linearSearch(arr, targetVal):
    for i in range(len(arr)):
        if arr[i] == targetVal:
            return i
    return -1

arr = [3, 7, 2, 9, 5]
targetVal = 9

result = linearSearch(arr, targetVal)

if result != -1:
    print("Value",targetVal,"found at index",result)
else:
    print("Value",targetVal,"not found")
    def partition(array, low, high):
    pivot = array[high]
    i = low - 1

    for j in range(low, high):
        if array[j] <= pivot:
            i += 1
            array[i], array[j] = array[j], array[i]

    array[i+1], array[high] = array[high], array[i+1]
    return i+1

def quicksort(array, low=0, high=None):
    if high is None:
        high = len(array) - 1

    if low < high:
        pivot_index = partition(array, low, high)
        quicksort(array, low, pivot_index-1)
        quicksort(array, pivot_index+1, high)

my_array = [64, 34, 25, 12, 22, 11, 90, 5]
quicksort(my_array)
print("Sorted array:", my_array)



