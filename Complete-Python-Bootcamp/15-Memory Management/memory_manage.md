#### Python Memory Management
Memory management in Python involves a combination of automatic garbage collection, reference counting, and various internal optimizations to efficiently manage memory allocation and deallocation. Understanding these mechanisms can help developers write more efficient and robust applications.

1. Key Concepts in Python Memory Management
2. Memory Allocation and Deallocation
3. Reference Counting
4. Garbage Collection
5. The gc Module
6. Memory Management Best Practices

#### Reference Counting
Reference counting is the primary method Python uses to manage memory. Each object in Python maintains a count of references pointing to it. When the reference count drops to zero, the memory occupied by the object is deallocated.


```python
import sys

a=[]
## 2 (one reference from 'a' and one from getrefcount())
print(sys.getrefcount(a))
```

    2



```python
b=a
print(sys.getrefcount(b))
```

    3



```python
del b
print(sys.getrefcount(a))
```

    2


#### Garbage Collection
Python includes a cyclic garbage collector to handle reference cycles. Reference cycles occur when objects reference each other, preventing their reference counts from reaching zero.


```python
import gc
## enable garbage collection
gc.enable()


```


```python
gc.disable()
```


```python
gc.collect()
```




    1036




```python
### Get garbage collection stats
print(gc.get_stats())
```

    [{'collections': 182, 'collected': 1611, 'uncollectable': 0}, {'collections': 16, 'collected': 255, 'uncollectable': 0}, {'collections': 2, 'collected': 1036, 'uncollectable': 0}]



```python
### get unreachable objects
print(gc.garbage)
```

    []


####  Memory Management Best Practices
1. Use Local Variables: Local variables have a shorter lifespan and are freed sooner than global variables.
2. Avoid Circular References: Circular references can lead to memory leaks if not properly managed.
3. Use Generators: Generators produce items one at a time and only keep one item in memory at a time, making them memory efficient.
4. Explicitly Delete Objects: Use the del statement to delete variables and objects explicitly.
5. Profile Memory Usage: Use memory profiling tools like tracemalloc and memory_profiler to identify memory leaks and optimize memory usage.


```python
## Handled Circular reference
import gc

class MyObject:
    def __init__(self, name):
        self.name = name
        print(f"Object {self.name} created")

    def __del__(self):
        print(f"Object {self.name} deleted")

# Create circular reference
obj1 = MyObject("obj1")
obj2 = MyObject("obj2")
obj1.ref = obj2
obj2.ref = obj1

del obj1
del obj2

## Manually trigger the garbage collection
gc.collect()






```

    Object obj1 created
    Object obj2 created
    Object obj1 deleted
    Object obj2 deleted
    Object obj1 deleted
    Object obj2 deleted
    Object obj1 deleted
    Object obj2 deleted


    gc: collectable <NameError 0x00000205D63FEF80>
    gc: collectable <traceback 0x00000205D69F5D80>
    gc: collectable <traceback 0x00000205D69F7980>
    gc: collectable <frame 0x00000205D646D240>
    gc: collectable <function 0x00000205D64FFD80>
    gc: collectable <frame 0x00000205D6453230>
    gc: collectable <frame 0x00000205D6A10CA0>
    gc: collectable <ExecutionResult 0x00000205D647D7F0>
    gc: collectable <frame 0x00000205D64B07C0>
    gc: collectable <list 0x00000205D6A03A00>
    gc: collectable <list 0x00000205D6A00640>
    gc: collectable <list 0x00000205D6A1C380>
    gc: collectable <function 0x00000205D642BA60>
    gc: collectable <list 0x00000205D6A03B80>
    gc: collectable <Delete 0x00000205D69F6B90>
    gc: collectable <Module 0x00000205D50EF310>
    gc: collectable <ExecutionInfo 0x00000205D647E2D0>
    gc: collectable <frame 0x00000205D629FC40>
    gc: collectable <cell 0x00000205D647CC10>
    gc: collectable <cell 0x00000205D647E3E0>
    gc: collectable <function 0x00000205D64FFE20>
    gc: collectable <Module 0x00000205D646B510>
    gc: collectable <cell 0x00000205D647D930>
    gc: collectable <Expr 0x00000205D69F4B90>
    gc: collectable <tuple 0x00000205D6A242C0>
    gc: collectable <tuple 0x00000205D6A1F540>
    gc: collectable <dict 0x00000205D69F5940>
    gc: collectable <dict 0x00000205D6468B40>
    gc: collectable <frame 0x00000205D6251BC0>
    gc: collectable <coroutine 0x00000205D6941F80>
    gc: collectable <tuple 0x00000205D6A1D280>
    gc: collectable <dict 0x00000205D69F5640>
    gc: collectable <dict 0x00000205D69F5C00>
    gc: collectable <list 0x00000205D69CAF40>
    gc: collectable <list 0x00000205D6A1C180>
    gc: collectable <list 0x00000205D6A02FC0>
    gc: collectable <frame 0x00000205D641EA40>
    gc: collectable <list 0x00000205D6A0D040>
    gc: collectable <Call 0x00000205D69F7690>
    gc: collectable <Name 0x00000205D69F4CD0>
    gc: collectable <frame 0x00000205D6A41560>
    gc: collectable <dict 0x00000205D69F5EC0>
    gc: collectable <dict 0x00000205D6994900>
    gc: collectable <frame 0x00000205D62458B0>
    gc: collectable <Name 0x00000205D69F5150>
    gc: collectable <list 0x00000205D6A040C0>
    gc: collectable <list 0x00000205D69F7040>
    gc: collectable <frame 0x00000205D624CAC0>
    gc: collectable <dict 0x00000205D6A0EC00>
    gc: collectable <method 0x00000205D69F6740>
    gc: collectable <method 0x00000205D69F4A40>
    gc: collectable <cell 0x00000205D64A4970>
    gc: collectable <dict 0x00000205D69F5D00>
    gc: collectable <Call 0x00000205D69F7810>
    gc: collectable <frame 0x00000205D64AAEA0>
    gc: collectable <list 0x00000205D64A00C0>
    gc: collectable <dict 0x00000205D69F6440>
    gc: collectable <dict 0x00000205D69F5240>
    gc: collectable <dict 0x00000205D69FA140>
    gc: collectable <dict 0x00000205D69F5500>
    gc: collectable <list 0x00000205D6A06E40>
    gc: collectable <list 0x00000205D6A07D40>
    gc: collectable <dict 0x00000205D69F5E80>
    gc: collectable <frame 0x00000205D6A3C5E0>
    gc: collectable <list 0x00000205D64A0680>
    gc: collectable <Attribute 0x00000205D69F5110>
    gc: collectable <list 0x00000205D6A1EE40>
    gc: collectable <list 0x00000205D6A019C0>
    gc: collectable <frame 0x00000205D6A42A80>
    gc: collectable <coroutine 0x00000205D641FA40>
    gc: collectable <dict 0x00000205D69F5E00>
    gc: collectable <Name 0x00000205D69F56D0>
    gc: collectable <tuple 0x00000205D65C2350>
    gc: collectable <Name 0x00000205D69F6590>
    gc: collectable <dict 0x00000205D69F4F00>
    gc: collectable <list 0x00000205D6488E80>
    gc: collectable <dict 0x00000205D69F5BC0>
    gc: collectable <Frame 0x00000205D62D9020>
    gc: collectable <Frame 0x00000205D62D8F70>
    gc: collectable <Frame 0x00000205D62D8EC0>
    gc: collectable <Frame 0x00000205D62D8E10>
    gc: collectable <Frame 0x00000205D62D8D60>
    gc: collectable <Frame 0x00000205D62D8C00>
    gc: collectable <Frame 0x00000205D62D8CB0>
    gc: collectable <cell 0x00000205D65C0D00>
    gc: collectable <function 0x00000205D6A607C0>
    gc: collectable <StyleMeta 0x00000205D597C500>
    gc: collectable <tuple 0x00000205D6B19670>
    gc: collectable <Terminal256Formatter 0x00000205D65C2210>
    gc: collectable <dict 0x00000205D6B25680>
    gc: collectable <list 0x00000205D6B2E0C0>
    gc: collectable <dict 0x00000205D6B2A680>
    gc: collectable <Options 0x00000205D64A66C0>
    gc: collectable <FrameInfo 0x00000205D65EC8C0>
    gc: collectable <tuple 0x00000205D65E9510>
    gc: collectable <dict 0x00000205D6B25C00>
    gc: collectable <tuple 0x00000205D663EDD0>
    gc: collectable <dict 0x00000205D6B2B240>
    gc: collectable <dict 0x00000205D6B29840>
    gc: collectable <list 0x00000205D1048840>
    gc: collectable <list 0x00000205D6B296C0>
    gc: collectable <list 0x00000205D6B24200>
    gc: collectable <list 0x00000205D6B29800>
    gc: collectable <list 0x00000205D6A2B340>
    gc: collectable <list 0x00000205D6B1EC00>
    gc: collectable <list 0x00000205D6B25F40>
    gc: collectable <list 0x00000205D6B29180>
    gc: collectable <list 0x00000205D6B1C180>
    gc: collectable <list 0x00000205D6B28B80>
    gc: collectable <list 0x00000205D6B0DB00>
    gc: collectable <list 0x00000205D6B1DC80>
    gc: collectable <list 0x00000205D6B1C100>
    gc: collectable <list 0x00000205D6B27F40>
    gc: collectable <list 0x00000205D6B1DE40>
    gc: collectable <list 0x00000205D6B1DA40>
    gc: collectable <list 0x00000205D6B0DD40>
    gc: collectable <list 0x00000205D6B13E80>
    gc: collectable <list 0x00000205D6AD1C00>
    gc: collectable <list 0x00000205D6B1E140>
    gc: collectable <list 0x00000205D6B1F580>
    gc: collectable <list 0x00000205D6B262C0>
    gc: collectable <list 0x00000205D6B24A00>
    gc: collectable <list 0x00000205D6B27E40>
    gc: collectable <list 0x00000205D6B299C0>
    gc: collectable <list 0x00000205D6B2A740>
    gc: collectable <list 0x00000205D6B1FA80>
    gc: collectable <list 0x00000205D6B1EF80>
    gc: collectable <list 0x00000205D6B12D00>
    gc: collectable <list 0x00000205D6B25CC0>
    gc: collectable <list 0x00000205D6B2A1C0>
    gc: collectable <list 0x00000205D6B1CD00>
    gc: collectable <list 0x00000205D6B1CB80>
    gc: collectable <list 0x00000205D6B1CDC0>
    gc: collectable <list 0x00000205D6B1CE80>
    gc: collectable <list 0x00000205D6B1CEC0>
    gc: collectable <list 0x00000205D6B1CC40>
    gc: collectable <list 0x00000205D6B1CF00>
    gc: collectable <list 0x00000205D6B1CF40>
    gc: collectable <list 0x00000205D6B1CF80>
    gc: collectable <list 0x00000205D6B1CFC0>
    gc: collectable <list 0x00000205D6B1D000>
    gc: collectable <list 0x00000205D6B1CA80>
    gc: collectable <list 0x00000205D6B1D040>
    gc: collectable <list 0x00000205D6B1D080>
    gc: collectable <list 0x00000205D6B1D0C0>
    gc: collectable <list 0x00000205D6B1D200>
    gc: collectable <list 0x00000205D6B1D280>
    gc: collectable <list 0x00000205D6B1D240>
    gc: collectable <list 0x00000205D6B1D1C0>
    gc: collectable <list 0x00000205D6B1D180>
    gc: collectable <list 0x00000205D6B1D2C0>
    gc: collectable <list 0x00000205D6B1FC40>
    gc: collectable <list 0x00000205D6B1DB40>
    gc: collectable <list 0x00000205D6B1E100>
    gc: collectable <list 0x00000205D6B1D500>
    gc: collectable <list 0x00000205D6B1E1C0>
    gc: collectable <list 0x00000205D6B1DE80>
    gc: collectable <list 0x00000205D6B1DF80>
    gc: collectable <list 0x00000205D6B1E240>
    gc: collectable <list 0x00000205D6B1D300>
    gc: collectable <list 0x00000205D6B1D900>
    gc: collectable <list 0x00000205D6B1E580>
    gc: collectable <list 0x00000205D6B1E400>
    gc: collectable <list 0x00000205D6B1E380>
    gc: collectable <list 0x00000205D6B1E500>
    gc: collectable <list 0x00000205D6B1E600>
    gc: collectable <list 0x00000205D6B1E300>
    gc: collectable <list 0x00000205D6B1E680>
    gc: collectable <list 0x00000205D6B1E6C0>
    gc: collectable <list 0x00000205D6B1E780>
    gc: collectable <list 0x00000205D6B1E7C0>
    gc: collectable <list 0x00000205D6B1E980>
    gc: collectable <list 0x00000205D6B1C040>
    gc: collectable <list 0x00000205D6B1D4C0>
    gc: collectable <list 0x00000205D6B1DFC0>
    gc: collectable <list 0x00000205D6B1C2C0>
    gc: collectable <list 0x00000205D6B1E740>
    gc: collectable <list 0x00000205D6B1E900>
    gc: collectable <list 0x00000205D6B1E880>
    gc: collectable <list 0x00000205D6B1E700>
    gc: collectable <list 0x00000205D6B1DCC0>
    gc: collectable <list 0x00000205D6B1ED40>
    gc: collectable <list 0x00000205D6B1EB00>
    gc: collectable <list 0x00000205D6B1EE80>
    gc: collectable <list 0x00000205D6B1EF40>
    gc: collectable <list 0x00000205D6B1F100>
    gc: collectable <list 0x00000205D6B1F340>
    gc: collectable <list 0x00000205D6B1F380>
    gc: collectable <list 0x00000205D6B1F440>
    gc: collectable <list 0x00000205D6B1E800>
    gc: collectable <list 0x00000205D6B1F8C0>
    gc: collectable <list 0x00000205D6B1D580>
    gc: collectable <list 0x00000205D6B1FEC0>
    gc: collectable <list 0x00000205D6B1E840>
    gc: collectable <list 0x00000205D6B1ED80>
    gc: collectable <list 0x00000205D6B1FBC0>
    gc: collectable <list 0x00000205D6B1F540>
    gc: collectable <list 0x00000205D6B1E5C0>
    gc: collectable <list 0x00000205D6B1F940>
    gc: collectable <list 0x00000205D6B2F680>
    gc: collectable <list 0x00000205D6B2F640>
    gc: collectable <list 0x00000205D6B2C080>
    gc: collectable <list 0x00000205D6B2C100>
    gc: collectable <list 0x00000205D6B2C1C0>
    gc: collectable <list 0x00000205D6B2C240>
    gc: collectable <list 0x00000205D6B2C2C0>
    gc: collectable <list 0x00000205D6B2C340>
    gc: collectable <list 0x00000205D6B2C3C0>
    gc: collectable <list 0x00000205D6B2C440>
    gc: collectable <list 0x00000205D6B2C180>
    gc: collectable <list 0x00000205D6B2C640>
    gc: collectable <list 0x00000205D6B2C4C0>
    gc: collectable <list 0x00000205D6B2C7C0>
    gc: collectable <list 0x00000205D6B2C6C0>
    gc: collectable <list 0x00000205D6B2C740>
    gc: collectable <list 0x00000205D6B2C940>
    gc: collectable <list 0x00000205D6B2CA80>
    gc: collectable <list 0x00000205D6B2CA00>
    gc: collectable <list 0x00000205D6B2CB40>
    gc: collectable <list 0x00000205D6B2CC40>
    gc: collectable <list 0x00000205D6B2CD00>
    gc: collectable <list 0x00000205D6B2CD80>
    gc: collectable <list 0x00000205D6B2CF40>
    gc: collectable <list 0x00000205D6B2CDC0>
    gc: collectable <list 0x00000205D6B2CE40>
    gc: collectable <list 0x00000205D6B2CEC0>
    gc: collectable <list 0x00000205D6B2D180>
    gc: collectable <list 0x00000205D6B2D200>
    gc: collectable <list 0x00000205D6B2D080>
    gc: collectable <list 0x00000205D6B2D2C0>
    gc: collectable <list 0x00000205D6B2D340>
    gc: collectable <list 0x00000205D6B2D4C0>
    gc: collectable <list 0x00000205D6B2D440>
    gc: collectable <list 0x00000205D6B2D3C0>
    gc: collectable <list 0x00000205D6B2D580>
    gc: collectable <list 0x00000205D6B2D6C0>
    gc: collectable <list 0x00000205D6B2D640>
    gc: collectable <list 0x00000205D6B2CE00>
    gc: collectable <list 0x00000205D6B2C8C0>
    gc: collectable <list 0x00000205D6B2D500>
    gc: collectable <list 0x00000205D6B2D900>
    gc: collectable <list 0x00000205D6B2DB40>
    gc: collectable <list 0x00000205D6B2D980>
    gc: collectable <list 0x00000205D6B2D800>
    gc: collectable <list 0x00000205D6B2DAC0>
    gc: collectable <list 0x00000205D6B2DC80>
    gc: collectable <list 0x00000205D6B2DD40>
    gc: collectable <list 0x00000205D6B2DDC0>
    gc: collectable <list 0x00000205D6B2DE40>
    gc: collectable <list 0x00000205D6B2DEC0>
    gc: collectable <list 0x00000205D6B2DF40>
    gc: collectable <list 0x00000205D6B2DA00>
    gc: collectable <list 0x00000205D6B2D100>
    gc: collectable <list 0x00000205D6B2E040>
    gc: collectable <list 0x00000205D6B2D780>
    gc: collectable <list 0x00000205D6B2E240>
    gc: collectable <list 0x00000205D6B2CB80>
    gc: collectable <list 0x00000205D6B2E300>
    gc: collectable <list 0x00000205D6B2D9C0>
    gc: collectable <tuple 0x00000205D65ED060>
    gc: collectable <_ctypes.PyCArrayType 0x00000205D597D480>
    gc: collectable <tuple 0x00000205D6B52520>
    gc: collectable <getset_descriptor 0x00000205D6B1D640>
    gc: collectable <getset_descriptor 0x00000205D6B62540>
    gc: collectable <StgDict 0x00000205D6B3B370>
    gc: collectable <tuple 0x00000205D65ED930>
    gc: collectable <_ctypes.PyCArrayType 0x00000205D597B1A0>
    gc: collectable <tuple 0x00000205D6B52160>
    gc: collectable <getset_descriptor 0x00000205D6B620C0>
    gc: collectable <getset_descriptor 0x00000205D6B62E00>
    gc: collectable <StgDict 0x00000205D6B7A9B0>
    gc: collectable <function 0x00000205D6B4DE40>
    gc: collectable <function 0x00000205D6B4DEE0>
    gc: collectable <tuple 0x00000205D65ED570>
    gc: collectable <dict 0x00000205D6B61D00>
    gc: collectable <type 0x00000205D597B580>
    gc: collectable <tuple 0x00000205D6B629C0>
    gc: collectable <getset_descriptor 0x00000205D6B59A80>
    gc: collectable <getset_descriptor 0x00000205D6B5ACC0>
    gc: collectable <MyObject 0x00000205D64A52E0>
    gc: collectable <MyObject 0x00000205D65E8C80>
    gc: collectable <MyObject 0x00000205D65E9AC0>
    gc: collectable <MyObject 0x00000205D65E8EC0>
    gc: collectable <dict 0x00000205D6B25500>
    gc: collectable <list 0x00000205D6ADC100>
    gc: collectable <list 0x00000205D6B48B80>
    gc: collectable <list 0x00000205D6B48BC0>
    gc: collectable <Line 0x00000205D647DC70>
    gc: collectable <Line 0x00000205D647E240>
    gc: collectable <Line 0x00000205D647D280>
    gc: collectable <list 0x00000205D6B1DA00>
    gc: collectable <cell 0x00000205D64A68F0>
    gc: collectable <RegexLexerMeta 0x00000205D5977F40>
    gc: collectable <tuple 0x00000205D6B1A610>
    gc: collectable <list 0x00000205D6B26140>
    gc: collectable <dict 0x00000205D6B49000>
    gc: collectable <tuple 0x00000205D6B45EC0>
    gc: collectable <tuple 0x00000205D6B45E80>
    gc: collectable <tuple 0x00000205D6B49080>
    gc: collectable <tuple 0x00000205D6B49040>
    gc: collectable <tuple 0x00000205D6B490C0>
    gc: collectable <tuple 0x00000205D6B49140>
    gc: collectable <tuple 0x00000205D6B49180>
    gc: collectable <list 0x00000205D6B48F80>
    gc: collectable <tuple 0x00000205D6B49BC0>
    gc: collectable <tuple 0x00000205D6B49540>
    gc: collectable <list 0x00000205D6498E00>
    gc: collectable <tuple 0x00000205D6B492C0>
    gc: collectable <tuple 0x00000205D6B491C0>
    gc: collectable <tuple 0x00000205D6B49240>
    gc: collectable <tuple 0x00000205D6B49B80>
    gc: collectable <builtin_method 0x00000205D6B43100>
    gc: collectable <tuple 0x00000205D6B49B40>
    gc: collectable <list 0x00000205D6442D40>
    gc: collectable <list 0x00000205D6B49300>
    gc: collectable <list 0x00000205D6B48880>
    gc: collectable <tuple 0x00000205D6B49440>
    gc: collectable <tuple 0x00000205D6B49100>
    gc: collectable <list 0x00000205D6B49340>
    gc: collectable <tuple 0x00000205D6B49280>
    gc: collectable <list 0x00000205D6B49600>
    gc: collectable <tuple 0x00000205D6B49380>
    gc: collectable <tuple 0x00000205D6B49900>
    gc: collectable <tuple 0x00000205D6B49940>
    gc: collectable <tuple 0x00000205D6B49A40>
    gc: collectable <tuple 0x00000205D6B49A80>
    gc: collectable <tuple 0x00000205D6B49D80>
    gc: collectable <list 0x00000205D6B49640>
    gc: collectable <list 0x00000205D6B48C00>
    gc: collectable <tuple 0x00000205D6B49E40>
    gc: collectable <list 0x00000205D6B498C0>
    gc: collectable <tuple 0x00000205D6B49E80>
    gc: collectable <tuple 0x00000205D6B4A0C0>
    gc: collectable <tuple 0x00000205D6B4A100>
    gc: collectable <tuple 0x00000205D6B4A140>
    gc: collectable <tuple 0x00000205D6B4A240>
    gc: collectable <tuple 0x00000205D6B4A340>
    gc: collectable <list 0x00000205D6B49840>
    gc: collectable <list 0x00000205D6B49680>
    gc: collectable <tuple 0x00000205D6B4A380>
    gc: collectable <tuple 0x00000205D6A1D300>
    gc: collectable <tuple 0x00000205D6B4A3C0>
    gc: collectable <list 0x00000205D6B496C0>
    gc: collectable <list 0x00000205D6B48D80>
    gc: collectable <tuple 0x00000205D6B4A500>
    gc: collectable <tuple 0x00000205D6B4A4C0>
    gc: collectable <tuple 0x00000205D6B4A580>
    gc: collectable <list 0x00000205D6B49800>
    gc: collectable <list 0x00000205D6B49880>
    gc: collectable <list 0x00000205D6B48B40>
    gc: collectable <tuple 0x00000205D6B4A680>
    gc: collectable <list 0x00000205D6B49980>
    gc: collectable <tuple 0x00000205D6B4A6C0>
    gc: collectable <tuple 0x00000205D6B4A780>
    gc: collectable <list 0x00000205D6B499C0>
    gc: collectable <tuple 0x00000205D6B4A9C0>
    gc: collectable <list 0x00000205D6B48AC0>
    gc: collectable <tuple 0x00000205D6B4AB00>
    gc: collectable <list 0x00000205D6B49AC0>
    gc: collectable <tuple 0x00000205D644C400>
    gc: collectable <tuple 0x00000205D6B4AAC0>
    gc: collectable <tuple 0x00000205D6B4A840>
    gc: collectable <tuple 0x00000205D6B4AA80>
    gc: collectable <tuple 0x00000205D6B4AB40>
    gc: collectable <list 0x00000205D6B49B00>
    gc: collectable <list 0x00000205D6B49400>
    gc: collectable <tuple 0x00000205D6B4AC40>
    gc: collectable <list 0x00000205D6B49EC0>
    gc: collectable <tuple 0x00000205D6B2BFC0>
    gc: collectable <tuple 0x00000205D6B4AC80>
    gc: collectable <tuple 0x00000205D6B4AE00>
    gc: collectable <tuple 0x00000205D6B4AF80>
    gc: collectable <tuple 0x00000205D6B4AEC0>
    gc: collectable <tuple 0x00000205D6B4AFC0>
    gc: collectable <tuple 0x00000205D6B4B000>
    gc: collectable <list 0x00000205D6B49F00>
    gc: collectable <list 0x00000205D6B48E40>
    gc: collectable <tuple 0x00000205D6B4B040>
    gc: collectable <list 0x00000205D6B4A180>
    gc: collectable <tuple 0x00000205D6A01480>
    gc: collectable <tuple 0x00000205D6B4B0C0>
    gc: collectable <tuple 0x00000205D6B4B100>
    gc: collectable <tuple 0x00000205D6B4B140>
    gc: collectable <tuple 0x00000205D6B4B180>
    gc: collectable <tuple 0x00000205D6B4B200>
    gc: collectable <tuple 0x00000205D6B4B240>
    gc: collectable <list 0x00000205D6B4A1C0>
    gc: collectable <list 0x00000205D6B48CC0>
    gc: collectable <tuple 0x00000205D6B4B280>
    gc: collectable <tuple 0x00000205D6B4B2C0>
    gc: collectable <tuple 0x00000205D6B4B340>
    gc: collectable <list 0x00000205D6B4A2C0>
    gc: collectable <list 0x00000205D6B4A300>
    gc: collectable <tuple 0x00000205D6B4B300>
    gc: collectable <tuple 0x00000205D6B2BD40>
    gc: collectable <tuple 0x00000205D6B4B3C0>
    gc: collectable <list 0x00000205D6B49C80>
    gc: collectable <tuple 0x00000205D6B4B380>
    gc: collectable <list 0x00000205D6B4A400>
    gc: collectable <tuple 0x00000205D6B4B440>
    gc: collectable <list 0x00000205D6B4A440>
    gc: collectable <tuple 0x00000205D6B4B4C0>
    gc: collectable <list 0x00000205D6B4A080>
    gc: collectable <tuple 0x00000205D6B4B500>
    gc: collectable <tuple 0x00000205D6B4B580>
    gc: collectable <list 0x00000205D6B4A540>
    gc: collectable <tuple 0x00000205D69F7A80>
    gc: collectable <tuple 0x00000205D6B4B5C0>
    gc: collectable <tuple 0x00000205D6B4B600>
    gc: collectable <tuple 0x00000205D6B4B640>
    gc: collectable <tuple 0x00000205D6B4B680>
    gc: collectable <tuple 0x00000205D6B4B700>
    gc: collectable <tuple 0x00000205D6B4B740>
    gc: collectable <tuple 0x00000205D6B4B780>
    gc: collectable <builtin_method 0x00000205D6B50680>
    gc: collectable <tuple 0x00000205D6B4B7C0>
    gc: collectable <list 0x00000205D6B4A5C0>
    gc: collectable <tuple 0x00000205D6B540C0>
    gc: collectable <tuple 0x00000205D6B4B940>
    gc: collectable <list 0x00000205D6B4A040>
    gc: collectable <Executing 0x00000205D64A7D70>
    gc: collectable <dict 0x00000205D6489E00>
    gc: collectable <tuple 0x00000205D65E9270>
    gc: collectable <builtin_method 0x00000205D6B42A70>
    gc: collectable <builtin_method 0x00000205D6B42AC0>
    gc: collectable <builtin_method 0x00000205D6B42B60>
    gc: collectable <builtin_method 0x00000205D6B42BB0>
    gc: collectable <builtin_method 0x00000205D6B42C00>
    gc: collectable <builtin_method 0x00000205D6B42C50>
    gc: collectable <builtin_method 0x00000205D6B42CA0>
    gc: collectable <builtin_method 0x00000205D6B42DE0>
    gc: collectable <builtin_method 0x00000205D6B42FC0>
    gc: collectable <builtin_method 0x00000205D6B42F70>
    gc: collectable <builtin_method 0x00000205D6B43010>
    gc: collectable <builtin_method 0x00000205D6B43060>
    gc: collectable <builtin_method 0x00000205D6B430B0>
    gc: collectable <builtin_method 0x00000205D6B431A0>
    gc: collectable <builtin_method 0x00000205D6B431F0>
    gc: collectable <builtin_method 0x00000205D6B43240>
    gc: collectable <builtin_method 0x00000205D6B43290>
    gc: collectable <builtin_method 0x00000205D6B432E0>
    gc: collectable <builtin_method 0x00000205D6B43330>
    gc: collectable <builtin_method 0x00000205D6B43380>
    gc: collectable <builtin_method 0x00000205D6B433D0>
    gc: collectable <builtin_method 0x00000205D6B43150>
    gc: collectable <builtin_method 0x00000205D6B43470>
    gc: collectable <builtin_method 0x00000205D6B434C0>
    gc: collectable <builtin_method 0x00000205D6B43510>
    gc: collectable <builtin_method 0x00000205D6B43560>
    gc: collectable <builtin_method 0x00000205D6B435B0>
    gc: collectable <builtin_method 0x00000205D6B43600>
    gc: collectable <builtin_method 0x00000205D6B43420>
    gc: collectable <builtin_method 0x00000205D6B436A0>
    gc: collectable <builtin_method 0x00000205D6B436F0>
    gc: collectable <builtin_method 0x00000205D6B43650>
    gc: collectable <builtin_method 0x00000205D6B43790>
    gc: collectable <builtin_method 0x00000205D6B437E0>
    gc: collectable <builtin_method 0x00000205D6B43740>
    gc: collectable <builtin_method 0x00000205D6B43880>
    gc: collectable <builtin_method 0x00000205D6B438D0>
    gc: collectable <builtin_method 0x00000205D6B43830>
    gc: collectable <builtin_method 0x00000205D6B43920>
    gc: collectable <builtin_method 0x00000205D6B43970>
    gc: collectable <builtin_method 0x00000205D6B439C0>
    gc: collectable <builtin_method 0x00000205D6B43A10>
    gc: collectable <builtin_method 0x00000205D6B43A60>
    gc: collectable <builtin_method 0x00000205D6B43AB0>
    gc: collectable <builtin_method 0x00000205D6B43B00>
    gc: collectable <builtin_method 0x00000205D6B43BA0>
    gc: collectable <builtin_method 0x00000205D6B43BF0>
    gc: collectable <builtin_method 0x00000205D6B43C40>
    gc: collectable <builtin_method 0x00000205D6B43C90>
    gc: collectable <builtin_method 0x00000205D6B43CE0>
    gc: collectable <builtin_method 0x00000205D6B43D30>
    gc: collectable <builtin_method 0x00000205D6B43D80>
    gc: collectable <builtin_method 0x00000205D6B43B50>
    gc: collectable <builtin_method 0x00000205D6B43E20>
    gc: collectable <builtin_method 0x00000205D6B43E70>
    gc: collectable <builtin_method 0x00000205D6B43EC0>
    gc: collectable <builtin_method 0x00000205D6B43F10>
    gc: collectable <builtin_method 0x00000205D6B43F60>
    gc: collectable <builtin_method 0x00000205D6B43FB0>
    gc: collectable <builtin_method 0x00000205D6B50040>
    gc: collectable <builtin_method 0x00000205D6B43DD0>
    gc: collectable <builtin_method 0x00000205D6B500E0>
    gc: collectable <builtin_method 0x00000205D6B50130>
    gc: collectable <builtin_method 0x00000205D6B50090>
    gc: collectable <builtin_method 0x00000205D6B501D0>
    gc: collectable <builtin_method 0x00000205D6B50220>
    gc: collectable <builtin_method 0x00000205D6B50180>
    gc: collectable <builtin_method 0x00000205D6B50270>
    gc: collectable <builtin_method 0x00000205D6B502C0>
    gc: collectable <builtin_method 0x00000205D6B50310>
    gc: collectable <builtin_method 0x00000205D6B50360>
    gc: collectable <builtin_method 0x00000205D6B503B0>
    gc: collectable <builtin_method 0x00000205D6B50400>
    gc: collectable <builtin_method 0x00000205D6B50450>
    gc: collectable <builtin_method 0x00000205D6B504A0>
    gc: collectable <builtin_method 0x00000205D6B504F0>
    gc: collectable <builtin_method 0x00000205D6B50540>
    gc: collectable <builtin_method 0x00000205D6B50590>
    gc: collectable <builtin_method 0x00000205D6B505E0>
    gc: collectable <builtin_method 0x00000205D6B50630>
    gc: collectable <builtin_method 0x00000205D6B50860>
    gc: collectable <builtin_method 0x00000205D6B50810>
    gc: collectable <function 0x00000205D6A63CE0>
    gc: collectable <dict 0x00000205D6498A40>
    gc: collectable <tuple 0x00000205D6B248C0>
    gc: collectable <cell 0x00000205D65EC550>
    gc: collectable <tuple 0x00000205D6B58800>
    gc: collectable <tuple 0x00000205D6B587C0>
    gc: collectable <tuple 0x00000205D6B672C0>
    gc: collectable <list 0x00000205D6B67D80>
    gc: collectable <tuple 0x00000205D6B628C0>
    gc: collectable <list 0x00000205D6B62100>
    gc: collectable <tuple 0x00000205D6B5B0C0>
    gc: collectable <list 0x00000205D6B5AF80>
    gc: collectable <tuple 0x00000205D6B5B000>
    gc: collectable <tuple 0x00000205D6B58BC0>
    gc: collectable <tuple 0x00000205D6B583C0>
    gc: collectable <list 0x00000205D6B5A540>
    gc: collectable <tuple 0x00000205D6B58A40>
    gc: collectable <tuple 0x00000205D6B59C80>
    gc: collectable <tuple 0x00000205D6B59640>
    gc: collectable <tuple 0x00000205D6B59580>
    gc: collectable <list 0x00000205D6B59280>
    gc: collectable <tuple 0x00000205D6B62500>
    gc: collectable <tuple 0x00000205D6B62480>
    gc: collectable <tuple 0x00000205D6B62BC0>
    gc: collectable <list 0x00000205D6B5A1C0>
    gc: collectable <tuple 0x00000205D6B62B80>
    gc: collectable <tuple 0x00000205D6B62B40>
    gc: collectable <list 0x00000205D6B58B80>
    gc: collectable <tuple 0x00000205D6B61780>
    gc: collectable <tuple 0x00000205D6B619C0>
    gc: collectable <list 0x00000205D6B5A340>
    gc: collectable <tuple 0x00000205D6B61540>
    gc: collectable <list 0x00000205D6B59E00>
    gc: collectable <tuple 0x00000205D6B60FC0>
    gc: collectable <tuple 0x00000205D6B60F00>
    gc: collectable <tuple 0x00000205D6B60B00>
    gc: collectable <tuple 0x00000205D6B60B40>
    gc: collectable <tuple 0x00000205D6B61A80>
    gc: collectable <list 0x00000205D6B5B280>
    gc: collectable <tuple 0x00000205D6B61880>
    gc: collectable <tuple 0x00000205D6B618C0>
    gc: collectable <tuple 0x00000205D6B61680>
    gc: collectable <tuple 0x00000205D6B61100>
    gc: collectable <tuple 0x00000205D6B610C0>
    gc: collectable <tuple 0x00000205D6B5A600>
    gc: collectable <type 0x00000205D597C8E0>
    gc: collectable <tuple 0x00000205D6B5AEC0>
    gc: collectable <MyObject 0x00000205D65C6C60>
    gc: collectable <MyObject 0x00000205D647D520>
    gc: collectable <builtin_method 0x00000205D6B50B80>
    gc: collectable <builtin_method 0x00000205D6B50E00>
    gc: collectable <builtin_method 0x00000205D6B50F90>
    gc: collectable <builtin_method 0x00000205D6B51940>
    gc: collectable <builtin_method 0x00000205D6B52840>
    gc: collectable <builtin_method 0x00000205D6B527F0>
    gc: collectable <builtin_method 0x00000205D6B52890>
    gc: collectable <builtin_method 0x00000205D6B528E0>
    gc: collectable <builtin_method 0x00000205D6B52930>
    gc: collectable <builtin_method 0x00000205D6B52980>
    gc: collectable <builtin_method 0x00000205D6B529D0>
    gc: collectable <builtin_method 0x00000205D6B52A20>
    gc: collectable <builtin_method 0x00000205D6B52A70>
    gc: collectable <builtin_method 0x00000205D6B52AC0>
    gc: collectable <builtin_method 0x00000205D6B52B10>
    gc: collectable <builtin_method 0x00000205D6B52B60>
    gc: collectable <builtin_method 0x00000205D6B52BB0>
    gc: collectable <builtin_method 0x00000205D6B52C00>
    gc: collectable <builtin_method 0x00000205D6B52C50>
    gc: collectable <builtin_method 0x00000205D6B52CA0>
    gc: collectable <builtin_method 0x00000205D6B52CF0>
    gc: collectable <builtin_method 0x00000205D6B52D40>
    gc: collectable <builtin_method 0x00000205D6B52D90>
    gc: collectable <builtin_method 0x00000205D6B52DE0>
    gc: collectable <builtin_method 0x00000205D6B52E30>
    gc: collectable <builtin_method 0x00000205D6B52E80>
    gc: collectable <builtin_method 0x00000205D6B52ED0>
    gc: collectable <builtin_method 0x00000205D6B52F20>
    gc: collectable <builtin_method 0x00000205D6B52F70>
    gc: collectable <builtin_method 0x00000205D6B52FC0>
    gc: collectable <list 0x00000205D64A3D40>
    gc: collectable <dict 0x00000205D6498FC0>
    gc: collectable <function 0x00000205D6A63C40>
    gc: collectable <function 0x00000205D6A637E0>
    gc: collectable <getset_descriptor 0x00000205D6B60900>
    gc: collectable <getset_descriptor 0x00000205D6B62F40>





    592




```python
## Generators For Memory Efficiency
#Generators allow you to produce items one at a time, using memory efficiently by only keeping one item in memory at a time.

def generate_numbers(n):
    for i in range(n):
        yield i

## using the generator
for num in generate_numbers(100000):
    print(num)
    if num>10:
        break
```

    0
    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11



```python
## Profiling Memory USage with tracemalloc
import tracemalloc

def create_list():
    return [i for i in range(10000)]

def main():
    tracemalloc.start()
    
    create_list()
    
    snapshot = tracemalloc.take_snapshot()
    top_stats = snapshot.statistics('lineno')
    
    print("[ Top 10 ]")
    for stat in top_stats[::]:
        print(stat)

```


```python
main()
```

    [ Top 10 ]
    e:\UDemy Final\python\venv\Lib\selectors.py:314: size=144 KiB, count=3, average=48.0 KiB
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\compilerop.py:174: size=11.2 KiB, count=122, average=94 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\builtin_trap.py:70: size=6512 B, count=1, average=6512 B
    e:\UDemy Final\python\venv\Lib\json\decoder.py:353: size=5812 B, count=92, average=63 B
    e:\UDemy Final\python\venv\Lib\threading.py:272: size=3800 B, count=10, average=380 B
    e:\UDemy Final\python\venv\Lib\codeop.py:118: size=3509 B, count=47, average=75 B
    e:\UDemy Final\python\venv\Lib\site-packages\zmq\sugar\attrsettr.py:45: size=3431 B, count=73, average=47 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\compilerop.py:86: size=3395 B, count=52, average=65 B
    e:\UDemy Final\python\venv\Lib\site-packages\traitlets\traitlets.py:731: size=2883 B, count=46, average=63 B
    e:\UDemy Final\python\venv\Lib\site-packages\jupyter_client\jsonutil.py:111: size=2050 B, count=41, average=50 B
    e:\UDemy Final\python\venv\Lib\site-packages\traitlets\traitlets.py:1543: size=2031 B, count=33, average=62 B
    e:\UDemy Final\python\venv\Lib\site-packages\jupyter_client\jsonutil.py:75: size=1456 B, count=7, average=208 B
    e:\UDemy Final\python\venv\Lib\re\_compiler.py:759: size=1360 B, count=5, average=272 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\iostream.py:346: size=1328 B, count=16, average=83 B
    e:\UDemy Final\python\venv\Lib\site-packages\traitlets\traitlets.py:1514: size=1320 B, count=11, average=120 B
    e:\UDemy Final\python\venv\Lib\site-packages\jupyter_client\session.py:1057: size=1276 B, count=11, average=116 B
    e:\UDemy Final\python\venv\Lib\site-packages\jupyter_client\session.py:100: size=1243 B, count=8, average=155 B
    e:\UDemy Final\python\venv\Lib\site-packages\zmq\sugar\socket.py:369: size=1152 B, count=5, average=230 B
    e:\UDemy Final\python\venv\Lib\site-packages\zmq\sugar\socket.py:809: size=1056 B, count=6, average=176 B
    e:\UDemy Final\python\venv\Lib\threading.py:568: size=864 B, count=16, average=54 B
    e:\UDemy Final\python\venv\Lib\threading.py:917: size=800 B, count=20, average=40 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\iostream.py:276: size=776 B, count=8, average=97 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\compiler.py:91: size=726 B, count=7, average=104 B
    e:\UDemy Final\python\venv\Lib\asyncio\events.py:84: size=648 B, count=6, average=108 B
    e:\UDemy Final\python\venv\Lib\_weakrefset.py:88: size=640 B, count=8, average=80 B
    e:\UDemy Final\python\venv\Lib\threading.py:1349: size=640 B, count=4, average=160 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\iostream.py:287: size=632 B, count=7, average=90 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\iostream.py:154: size=568 B, count=1, average=568 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\interactiveshell.py:3104: size=520 B, count=4, average=130 B
    e:\UDemy Final\python\venv\Lib\threading.py:1027: size=480 B, count=8, average=60 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\history.py:782: size=440 B, count=2, average=220 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\kernelbase.py:775: size=424 B, count=2, average=212 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\history.py:836: size=416 B, count=6, average=69 B
    e:\UDemy Final\python\venv\Lib\site-packages\zmq\sugar\context.py:354: size=416 B, count=4, average=104 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\history.py:790: size=416 B, count=1, average=416 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\history.py:789: size=416 B, count=1, average=416 B
    e:\UDemy Final\python\venv\Lib\fnmatch.py:46: size=400 B, count=5, average=80 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\history.py:783: size=393 B, count=1, average=393 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\interactiveshell.py:3334: size=376 B, count=1, average=376 B
    e:\UDemy Final\python\venv\Lib\threading.py:262: size=360 B, count=5, average=72 B
    e:\UDemy Final\python\venv\Lib\threading.py:261: size=360 B, count=5, average=72 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\ipkernel.py:362: size=360 B, count=1, average=360 B
    e:\UDemy Final\python\venv\Lib\threading.py:269: size=344 B, count=3, average=115 B
    e:\UDemy Final\python\venv\Lib\site-packages\dateutil\parser\_parser.py:1195: size=336 B, count=7, average=48 B
    e:\UDemy Final\python\venv\Lib\threading.py:912: size=320 B, count=8, average=40 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\interactiveshell.py:3566: size=320 B, count=5, average=64 B
    e:\UDemy Final\python\venv\Lib\asyncio\base_events.py:792: size=312 B, count=3, average=104 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\iostream.py:527: size=304 B, count=4, average=76 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\interactiveshell.py:3517: size=296 B, count=1, average=296 B
    e:\UDemy Final\python\venv\Lib\site-packages\tornado\queues.py:248: size=288 B, count=2, average=144 B
    e:\UDemy Final\python\venv\Lib\asyncio\base_events.py:427: size=288 B, count=2, average=144 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\iostream.py:142: size=288 B, count=1, average=288 B
    e:\UDemy Final\python\venv\Lib\fnmatch.py:185: size=280 B, count=5, average=56 B
    e:\UDemy Final\python\venv\Lib\fnmatch.py:52: size=280 B, count=5, average=56 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\kernelbase.py:534: size=264 B, count=1, average=264 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\kernelbase.py:435: size=248 B, count=1, average=248 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\iostream.py:121: size=248 B, count=1, average=248 B
    e:\UDemy Final\python\venv\Lib\threading.py:894: size=244 B, count=4, average=61 B
    <frozen ntpath>:66: size=240 B, count=5, average=48 B
    e:\UDemy Final\python\venv\Lib\site-packages\zmq\sugar\socket.py:806: size=240 B, count=3, average=80 B
    e:\UDemy Final\python\venv\Lib\logging\__init__.py:1622: size=240 B, count=1, average=240 B
    C:\Users\win10\AppData\Local\Temp\ipykernel_37980\3835544042.py:7: size=232 B, count=2, average=116 B
    C:\Users\win10\AppData\Local\Temp\ipykernel_37980\3835544042.py:4: size=232 B, count=2, average=116 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\kernelbase.py:545: size=232 B, count=1, average=232 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\zmqshell.py:549: size=224 B, count=3, average=75 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\compilerop.py:171: size=216 B, count=3, average=72 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\interactiveshell.py:3223: size=208 B, count=4, average=52 B
    e:\UDemy Final\python\venv\Lib\site-packages\tornado\platform\asyncio.py:235: size=208 B, count=3, average=69 B
    C:\Users\win10\AppData\Local\Temp\ipykernel_37980\811388706.py:22: size=208 B, count=2, average=104 B
    C:\Users\win10\AppData\Local\Temp\ipykernel_37980\3581627739.py:22: size=208 B, count=2, average=104 B
    C:\Users\win10\AppData\Local\Temp\ipykernel_37980\2565588716.py:22: size=208 B, count=2, average=104 B
    C:\Users\win10\AppData\Local\Temp\ipykernel_37980\2547200138.py:22: size=208 B, count=2, average=104 B
    e:\UDemy Final\python\venv\Lib\site-packages\jupyter_client\session.py:1085: size=208 B, count=1, average=208 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\kernelbase.py:770: size=208 B, count=1, average=208 B
    e:\UDemy Final\python\venv\Lib\asyncio\futures.py:418: size=200 B, count=5, average=40 B
    e:\UDemy Final\python\venv\Lib\site-packages\jupyter_client\session.py:688: size=194 B, count=2, average=97 B
    e:\UDemy Final\python\venv\Lib\site-packages\jupyter_client\session.py:750: size=192 B, count=2, average=96 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\interactiveshell.py:3224: size=176 B, count=4, average=44 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\kernelbase.py:1182: size=173 B, count=2, average=86 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\compilerop.py:172: size=168 B, count=6, average=28 B
    e:\UDemy Final\python\venv\Lib\threading.py:969: size=160 B, count=1, average=160 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\kernelbase.py:570: size=160 B, count=1, average=160 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\interactiveshell.py:3577: size=160 B, count=1, average=160 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\interactiveshell.py:3493: size=160 B, count=1, average=160 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\interactiveshell.py:3237: size=160 B, count=1, average=160 B
    e:\UDemy Final\python\venv\Lib\asyncio\futures.py:394: size=160 B, count=1, average=160 B
    e:\UDemy Final\python\venv\Lib\asyncio\futures.py:387: size=160 B, count=1, average=160 B
    e:\UDemy Final\python\venv\Lib\asyncio\futures.py:381: size=160 B, count=1, average=160 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\iostream.py:722: size=144 B, count=2, average=72 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\async_helpers.py:151: size=142 B, count=3, average=47 B
    e:\UDemy Final\python\venv\Lib\threading.py:1016: size=140 B, count=5, average=28 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\interactiveshell.py:3509: size=128 B, count=3, average=43 B
    e:\UDemy Final\python\venv\Lib\site-packages\jupyter_client\jsonutil.py:73: size=128 B, count=2, average=64 B
    e:\UDemy Final\python\venv\Lib\threading.py:121: size=120 B, count=2, average=60 B
    e:\UDemy Final\python\venv\Lib\site-packages\traitlets\traitlets.py:1540: size=120 B, count=2, average=60 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\kernelbase.py:318: size=120 B, count=2, average=60 B
    e:\UDemy Final\python\venv\Lib\site-packages\zmq\eventloop\zmqstream.py:652: size=120 B, count=1, average=120 B
    e:\UDemy Final\python\venv\Lib\inspect.py:265: size=120 B, count=1, average=120 B
    e:\UDemy Final\python\venv\Lib\asyncio\base_events.py:755: size=120 B, count=1, average=120 B
    e:\UDemy Final\python\venv\Lib\threading.py:1020: size=112 B, count=4, average=28 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\ipkernel.py:770: size=112 B, count=4, average=28 B
    e:\UDemy Final\python\venv\Lib\site-packages\jupyter_client\session.py:989: size=111 B, count=2, average=56 B
    e:\UDemy Final\python\venv\Lib\site-packages\zmq\sugar\socket.py:755: size=96 B, count=2, average=48 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\interactiveshell.py:3375: size=96 B, count=2, average=48 B
    e:\UDemy Final\python\venv\Lib\warnings.py:189: size=96 B, count=1, average=96 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\history.py:805: size=90 B, count=2, average=45 B
    e:\UDemy Final\python\venv\Lib\site-packages\jupyter_client\session.py:996: size=88 B, count=2, average=44 B
    e:\UDemy Final\python\venv\Lib\tracemalloc.py:551: size=72 B, count=1, average=72 B
    e:\UDemy Final\python\venv\Lib\tracemalloc.py:528: size=72 B, count=1, average=72 B
    e:\UDemy Final\python\venv\Lib\tracemalloc.py:477: size=72 B, count=1, average=72 B
    e:\UDemy Final\python\venv\Lib\tracemalloc.py:420: size=72 B, count=1, average=72 B
    e:\UDemy Final\python\venv\Lib\tracemalloc.py:312: size=72 B, count=1, average=72 B
    e:\UDemy Final\python\venv\Lib\tracemalloc.py:225: size=72 B, count=1, average=72 B
    e:\UDemy Final\python\venv\Lib\tracemalloc.py:220: size=72 B, count=1, average=72 B
    e:\UDemy Final\python\venv\Lib\tracemalloc.py:215: size=72 B, count=1, average=72 B
    e:\UDemy Final\python\venv\Lib\tracemalloc.py:212: size=72 B, count=1, average=72 B
    e:\UDemy Final\python\venv\Lib\tracemalloc.py:203: size=72 B, count=1, average=72 B
    e:\UDemy Final\python\venv\Lib\tracemalloc.py:187: size=72 B, count=1, average=72 B
    e:\UDemy Final\python\venv\Lib\tracemalloc.py:172: size=72 B, count=1, average=72 B
    e:\UDemy Final\python\venv\Lib\tracemalloc.py:155: size=72 B, count=1, average=72 B
    e:\UDemy Final\python\venv\Lib\tracemalloc.py:151: size=72 B, count=1, average=72 B
    e:\UDemy Final\python\venv\Lib\tracemalloc.py:147: size=72 B, count=1, average=72 B
    e:\UDemy Final\python\venv\Lib\tracemalloc.py:66: size=72 B, count=1, average=72 B
    e:\UDemy Final\python\venv\Lib\tracemalloc.py:52: size=72 B, count=1, average=72 B
    e:\UDemy Final\python\venv\Lib\tracemalloc.py:37: size=72 B, count=1, average=72 B
    e:\UDemy Final\python\venv\Lib\tracemalloc.py:13: size=72 B, count=1, average=72 B
    e:\UDemy Final\python\venv\Lib\threading.py:271: size=72 B, count=1, average=72 B
    e:\UDemy Final\python\venv\Lib\threading.py:267: size=72 B, count=1, average=72 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\history.py:851: size=72 B, count=1, average=72 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\history.py:837: size=72 B, count=1, average=72 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\history.py:834: size=72 B, count=1, average=72 B
    e:\UDemy Final\python\venv\Lib\json\encoder.py:224: size=72 B, count=1, average=72 B
    C:\Users\win10\AppData\Local\Temp\ipykernel_37980\451043146.py:0: size=72 B, count=1, average=72 B
    e:\UDemy Final\python\venv\Lib\asyncio\base_events.py:1935: size=64 B, count=2, average=32 B
    e:\UDemy Final\python\venv\Lib\site-packages\zmq\sugar\socket.py:810: size=64 B, count=1, average=64 B
    e:\UDemy Final\python\venv\Lib\site-packages\zmq\eventloop\zmqstream.py:640: size=64 B, count=1, average=64 B
    e:\UDemy Final\python\venv\Lib\site-packages\zmq\eventloop\zmqstream.py:561: size=64 B, count=1, average=64 B
    e:\UDemy Final\python\venv\Lib\site-packages\jupyter_client\session.py:1053: size=64 B, count=1, average=64 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\kernelbase.py:721: size=64 B, count=1, average=64 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\kernelbase.py:69: size=64 B, count=1, average=64 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\ipkernel.py:384: size=64 B, count=1, average=64 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\ipkernel.py:383: size=64 B, count=1, average=64 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\ipkernel.py:381: size=64 B, count=1, average=64 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\ipkernel.py:294: size=64 B, count=1, average=64 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\ipkernel.py:291: size=64 B, count=1, average=64 B
    e:\UDemy Final\python\venv\Lib\site-packages\decorator.py:232: size=64 B, count=1, average=64 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\interactiveshell.py:3303: size=64 B, count=1, average=64 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\interactiveshell.py:3300: size=64 B, count=1, average=64 B
    e:\UDemy Final\python\venv\Lib\tokenize.py:537: size=56 B, count=1, average=56 B
    e:\UDemy Final\python\venv\Lib\site-packages\traitlets\traitlets.py:1534: size=56 B, count=1, average=56 B
    e:\UDemy Final\python\venv\Lib\site-packages\jupyter_client\session.py:1088: size=56 B, count=1, average=56 B
    e:\UDemy Final\python\venv\Lib\site-packages\jupyter_client\session.py:738: size=56 B, count=1, average=56 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\interactiveshell.py:3498: size=56 B, count=1, average=56 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\history.py:866: size=56 B, count=1, average=56 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\completer.py:1120: size=56 B, count=1, average=56 B
    e:\UDemy Final\python\venv\Lib\selectors.py:323: size=56 B, count=1, average=56 B
    e:\UDemy Final\python\venv\Lib\site-packages\jupyter_client\session.py:200: size=48 B, count=1, average=48 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\interactiveshell.py:3505: size=48 B, count=1, average=48 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\history.py:835: size=48 B, count=1, average=48 B
    e:\UDemy Final\python\venv\Lib\concurrent\futures\_base.py:330: size=48 B, count=1, average=48 B
    e:\UDemy Final\python\venv\Lib\site-packages\zmq\sugar\attrsettr.py:29: size=47 B, count=1, average=47 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\prefilter.py:317: size=47 B, count=1, average=47 B
    e:\UDemy Final\python\venv\Lib\site-packages\jupyter_client\session.py:603: size=32 B, count=1, average=32 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\iostream.py:637: size=32 B, count=1, average=32 B
    e:\UDemy Final\python\venv\Lib\site-packages\ipykernel\iostream.py:168: size=32 B, count=1, average=32 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\interactiveshell.py:3503: size=32 B, count=1, average=32 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\history.py:793: size=32 B, count=1, average=32 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\completer.py:2813: size=32 B, count=1, average=32 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\completer.py:881: size=32 B, count=1, average=32 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\compilerop.py:192: size=32 B, count=1, average=32 B
    e:\UDemy Final\python\venv\Lib\concurrent\futures\_base.py:421: size=32 B, count=1, average=32 B
    e:\UDemy Final\python\venv\Lib\asyncio\base_events.py:758: size=32 B, count=1, average=32 B
    e:\UDemy Final\python\venv\Lib\site-packages\IPython\core\interactiveshell.py:3485: size=8 B, count=1, average=8 B



```python

```
