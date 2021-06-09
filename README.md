# 8thjune2021_devops
import ctypes
x=10
print('X= ',x)
print(id(x))
#print by memory address
print(ctypes.cast(id(x),ctypes.py_object).value)
