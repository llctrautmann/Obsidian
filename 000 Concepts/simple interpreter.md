---
title: simple interpreter
date:
  - 28-03-2024
time: 20:21
author: Luca Trautmann
tags: 
series: 
chapter: 
status: Incomplete
modified: 2024-03-28
---
# simple interpreter
```python
class byte:

def __init__(self):
	self.value = 0

def increment(self):
	self.value += 1
	self.truncate()

def decrement(self):
	self.value -= 1
	self.truncate()  

def truncate(self):
	self.value = self.value % 256

def return_value(self):
	return self.value

def __str__(self):
	return f"{self.value}"

  

class Controller:
	def __init__(self, input_string):
		self.memory_len = 10000
		self.ram = [byte() for x in range(len(self.memory_len))]

```