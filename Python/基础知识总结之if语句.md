**4. if 语句**

- 一个简单示例

  下面的代码遍历一个列表，并以首字母大写的方式打印其中的战队名，但对于战队名 'ig' ，以全大写的方式打印

  ```python
  a = ['rng','ig','edg','rw']
  for b in a:
      if b == 'ig':
          print(b.upper())
      else:
          print(b.title()
               
  Rng
  IG
  Edg
  Rw
  ```

- 条件测试

  条 if 语句的核心都是一个值为 True 或 False 的表达式，这种表达式被称为 条件测试 。 Python 根据条件测试的值为 True 还是 False 来决定是否执行 if 语句中的代码。如果条件测试的值为 True ， Python 就执行紧跟在 if 语句后面的代码；如果为 False ， Python 就忽略这些代码

  ```python
  a = '1'
  print(a == '1')
  print(a == '2')
  
  True
  False
  ```

- 检查是否相等时不考虑大小写

  如果大小写无关紧要，而只想检查变量的值，可将变量的值转换为小写，再进行比较

  ```python
  a = 'Rng'
  print(a == 'rng')
  print(a.lower() == 'rng')
  print(a)
  
  False
  True
  Rng
  ```

- 检查是否不相等

  要判断两个值是否不等，可结合使用惊叹号和等号（ != ），其中的惊叹号表示 不 ，在很多编程语言中都如此

  ```python
  a = 'Rng'
  if a != 'Ig':
      print("Rng")
  
  Rng
  ```

- 比较数字

  条件语句中可包含各种数学比较，如小于、等于、大于

  ```python
  a = 5
  print(a == 5)
  print(a < 5)
  print(a > 5)
  
  True
  False
  False
  ```

- 检查多个条件

  要检查是否两个条件都为 True ，可使用关键字 and 将两个条件测试合而为一；如果每个测试都通过了，整个表达式就为 True ；如果至少有一个测试没有通过，整个表达式就
  为 False

  ```python
  a = 5
  b = 8
  print(a > 4 and b < 9)
  print(a > 5 and b < 9)
  print(a > 4 and b < 7)
  
  True
  False
  False
  ```

  关键字 or 也能够让你检查多个条件，但只要至少有一个条件满足，就能通过整个测试。仅当两个测试都没有通过时，使用 or 的表达式才为 False 

  ```python
  a = 5
  b = 8
  print(a > 4 or b < 7)
  print(a > 5 or b < 9)
  print(a > 5 or b < 7)
  
  True
  True
  False
  ```

- 检查特定值是否包含在列表中

  ```python
  a = ['rng','ig','edg','rw']
  b = 'omg'
  print('we' in a)
  print('rng' in a)
  if b not in a:
      print(b.title() + " can not find in a list!")
      
  False
  True
  Omg can not find in a list!
  ```

- 布尔表达式

  随着你对编程的了解越来越深入，将遇到术语 布尔表达式 ，它不过是条件测试的别名。与条件表达式一样，布尔表达式的结果要么为 True ，要么为 False 

- if-else  语句

  经常需要在条件测试通过了时执行一个操作，并在没有通过时执行另一个操作；在这种情况下，可使用 Python 提供的 if-else 语句。 if-else 语句块类似于简单的 if 语句，但其中的 else 语句让你能够指定条件测试未通过时要执行的操作

  ```python
  age = 18
  if age >= 18:
      print("You are a man!")
  else:
      print("You are a child!")
      
  You are a man!
  ```

- if-elif-else  结构

  经常需要检查超过两个的情形，为此可使用 Python 提供的 if-elif-else 结构。 Python 只执行 if-elif-else 结构中的一个代码块，它依次检查每个条件测试，直到遇到通过了的条件测试。测试通过后， Python 将执行紧跟在它后面的代码，并跳过余下的测试

  ```python
  age = 18
  if age < 18:
      print("You are a child!")
  elif age == 18:
      print("You are a boy!")
  else:
      print("You are a man")
      
  You are a boy!
  ```

- 省略 else  代码块

  Python 并不要求 if-elif 结构后面必须有 else 代码块。在有些情况下， else 代码块很有用；而在其他一些情况下，使用一条 elif 语句来处理特定的情形更清晰 , else 是一条包罗万象的语句，只要不满足任何 if 或 elif 中的条件测试，其中的代码就会执行，这可能会引入无效甚至恶意的数据。如果知道最终要测试的条件，应考虑使用一个 elif 代码块来代替 else 代码块。这样，你就可以肯定，仅当满足相应的条件时，你的代码才会执行

  ```python
  age = 15
  if age < 18:
      print("You are a child!")
  elif age == 18:
      print("You are a boy!")
  elif age > 18:
      print("You are a man")
      
  You are a child!
  ```

- 测试多个条件

  if-elif-else 结构功能强大，但仅适合用于只有一个条件满足的情况：遇到通过了的测试后， Python 就跳过余下的测试。这种行为很好，效率很高，让你能够测试一个特定的条件。然而，有时候必须检查你关心的所有条件。在这种情况下，应使用一系列不包含 elif 和 else 代码块的简单 if 语句。在可能有多个条件为 True ，且你需要在每个条件为 True时都采取相应措施时，适合使用这种方法

  ```python
  S8 = ['rng','ig','edg']
  if 'rng' in S8:
      print("Come on , RNG")
  if 'ig' in S8:
      print("Come on , IG")
  if 'rw' in S8:
      print("Come on , RW")
  
  print("Come on LPL !")
  
  Come on , RNG
  Come on , IG
  Come on LPL !
  ```

- 使用 if 语句处理列表

  检查特殊元素

  ```python
  a = ['apple','banana','orange']
  for b in a:
      print("Adding " + b + "!")
  print("\nFinish making your fruit!")
  
  Adding apple!
  Adding banana!
  Adding orange!
  
  Finish making your fruit!
  ```

- 使用多个列表

  顾客的要求往往五花八门，在比萨配料方面尤其如此。如果顾客要在比萨中添加炸薯条，该怎么办呢？可使用列表和 if 语句来确定能否满足顾客的要求。来看看在制作比萨前如何拒绝怪异的配料要求。下面的示例定义了两个列表，其中第一个列表包含比萨店供应的配料，而第二个列表包含顾客点的配料。这次对于 requested_toppings 中的每个元素，都检查它是否是比萨店供应的配料，再决定是否在比萨中添加它

  ```python
  available_toppings = ['mushrooms', 'olives', 'green peppers','pepperoni', 'pineapple', 'extra cheese']
  requested_toppings = ['mushrooms', 'french fries', 'extra cheese']
  for requested_topping in requested_toppings:
      if requested_topping in available_toppings:
          print("Adding " + requested_topping + ".")
      else:
          print("Sorry, we don't have " + requested_topping + ".")
  print("\nFinished making your pizza!")
  
  Adding mushrooms.
  Sorry, we don't have french fries.
  Adding extra cheese.
  
  Finished making your pizza!
  ```
