# WAJD - Data Structure and Algorithm Game
Platform-Puzzle Educational Game developed in Godot 4
![](https://user-images.githubusercontent.com/64715936/278706322-7c3f7beb-8dee-4550-ae02-e8ec1213f944.png)
## About
Solve logical programming puzzles with limited time, jumping between platforms and lifting numbered boxes following the chosen algorithm.
### Rules
- Limited time between each stage: *1 minute*.
- The player must jump between platforms and organize 5 numbered boxes with randomly generated numbers in ascending order.
- The player can lift and drop only one box at a time.
- The way the player organizes these boxes will follow a programming algorithm.
- Each step must result in the array that the algorithm would generate during its execution.
- In the last stage, if all boxes are in the correct position: the player wins.
## Controls
Keyboard:
* ``Directional arrows (← ↑ →)``: walk and jump.
* ``Space``: lift a nearby box.
* ``CTRL``: drop a box you have lifted onto a platform.
* ``H``: help (receive the answer for the current step in array form for 10 seconds).
* ``ESC``: pause.
## Sorting Algorithms
### Bubble Sort
```python
func bubble_sort(arr):
	var n = arr.size()
	var swapped
	while swapped != false:
		swapped = false
		for i in range(1, n):
			if arr[i-1] > arr[i]:
				var temp = arr[i - 1]
				arr[i - 1] = arr[i]
				arr[i] = temp
				swapped = true
```
### Selection Sort
```python
func selection_sort(arr):
	var temp_arr = []
	var n = arr.size()
	var lower
	var temp
	for i in range(n):
		lower = i
		for j in range(i+1, n):
			if arr[j] < arr[lower]:
				lower = j
		if arr[i] != arr[lower]:
			temp = arr[i]
			arr[i] = arr[lower]
			arr[lower] = temp
```
### Shaker Sort
```python
func shaker_sort(arr):
	var temp_arr = []
	var n = arr.size()
	var temp
	var swap: bool
	swap = true
	while(swap):
		swap = false
		#left-right
		for i in range(n-1):
			if arr[i] > arr[i+1]:
				temp = arr[i]
				arr[i] = arr[i + 1]
				arr[i + 1] = temp
				swap = true
		if not swap:
			break
		swap = false
		#right-left
		for i in range(n-2, 0, -1):
			if arr[i] > arr[i+1]:
				temp = arr[i]
				arr[i] = arr[i+1]
				arr[i+1] = temp
				swap = true
```
