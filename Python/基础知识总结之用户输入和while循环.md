**6 . 用户输入和 while  循环**

- 函数 input() 的工作原理

  函数 input() 让程序暂停运行，等待用户输入一些文本。获取用户输入后， Python 将其存储在一个变量中，以方便你使用

  ```python
  message = input("Tell me something , and I will repeat it back to you : ")
  print(message)
  
  Tell me something , and I will repeat it back to you : hello word !
  hello word !
  ```

- 编写清晰的程序

  每当你使用函数 input() 时，都应指定清晰而易于明白的提示，准确地指出你希望用户提供什么样的信息 —— 指出用户该输入任何信息的提示都行，如下所示

  ```python
  name = input("Please enter your name : ")
  print("Hello, " + name + " !")
  
  Please enter your name : mao
  Hello, mao !
  ```

  有时候，提示可能超过一行，例如，你可能需要指出获取特定输入的原因。在这种情况下，可将提示存储在一个变量中，再将该变量传递给函数 input() 。这样，即便提示超过一行， input() 语句也非常清晰

  ```python
  prompt = "Who are you ? "
  prompt += "\nTell me : "
  
  name = input(prompt)
  print("\nHello, " + name + " !")
  
  Who are you ? 
  Tell me : mao
  
  Hello, mao !
  ```

- 使用 int()  来获取数值输入

  使用函数 input() 时， Python 将用户输入解读为字符串。请看下面让用户输入其年龄的解释器会话

  ```python
  age = input("How old are you ? ")
  age = int(age)
  print(age >= 18)
  
  How old are you ? 21
  True
  ```

- 求模运算符

  处理数值信息时， 求模运算符 （ % ）是一个很有用的工具，它将两个数相除并返回余数

  ```python
  print(4 % 3)
  print(5 % 3)
  print(6 % 3)
  print(7 % 3)
  
  1
  2
  0
  1
  ```

  如果一个数可被另一个数整除，余数就为 0 ，因此求模运算符将返回 0 。你可利用这一点来判断一个数是奇数还是偶数

  ```python
  number = input("Enter a number, and I'll tell you if it's even or odd: ")
  number = int(number)
  if number % 2 == 0:
      print("\nThe number " + str(number) + " is even.")
  else:
      print("\nThe number " + str(number) + " is odd.")
      
  Enter a number, and I'll tell you if it's even or odd: 101
  
  The number 101 is odd.
  ```

- 使用 while  循环

  for 循环用于针对集合中的每个元素都一个代码块，而 while 循环不断地运行，直到指定的条件不满足为止

  ```python
  a = 1
  while a <= 5:
      print(a)
      a += 1
      
  1
  2
  3
  4
  5
  ```

- 让用户选择何时退出

  可使用 while 循环让程序在用户愿意时不断地运行，如下面的程序所示。我们在其中定义了一个退出值，只要用户输入的不是这个值，程序就接着运行

  ```python
  prompt = "\nTell me something, and I will repeat it back to you:"
  prompt += "\nEnter 'quit' to end the program. "
  
  message = ""
  while message != 'quit':
      message = input(prompt)
      if message != 'quit':
          print(message)
          
  Tell me something, and I will repeat it back to you:
  Enter 'quit' to end the program. hello
  hello
  
  Tell me something, and I will repeat it back to you:
  Enter 'quit' to end the program. quit
  ```

- 使用标志

  在要求很多条件都满足才继续运行的程序中，可定义一个变量，用于判断整个程序是否处于活动状态。这个变量被称为 标志 ，充当了程序的交通信号灯。你可让程序在标志为 True 时继续运行，并在任何事件导致标志的值为 False 时让程序停止运行。这样，在 while 语句中就只需检查一个条件 —— 标志的当前值是否为 True ，并将所有测试（是否发生了应将标志设置为 False 的事件）都放在其他地方，从而让程序变得更为整洁

  ```python
  prompt = "\nTell me something, and I will repeat it back to you:"
  prompt += "\nEnter 'quit' to end the program. "
  
  active = True
  while active:
      message = input(prompt)
      if message == 'quit':
          active = False
      else:
          print(message)
          
  Tell me something, and I will repeat it back to you:
  Enter 'quit' to end the program. hello
  hello
  
  Tell me something, and I will repeat it back to you:
  Enter 'quit' to end the program. quit
  ```

- 使用 break  退出循环

  要立即退出 while 循环，不再运行循环中余下的代码，也不管条件测试的结果如何，可使用 break 语句。 break 语句用于控制程序流程，可使用它来控制哪些代码行将执行，哪些代码行不执行，从而让程序按你的要求执行你要执行的代码

  ```python
  prompt = "\nPlease enter the name of a city you have visited:"
  prompt += "\n(Enter 'quit' when you are finished.) "
  
  while True:
      a = input(prompt)
      if a == 'quit':
          break
      else:
          print("I'd love to go to " + a.title() + " !")
          
  Please enter the name of a city you have visited:
  (Enter 'quit' when you are finished.) Beijing
  I'd love to go to Beijing !
  
  Please enter the name of a city you have visited:
  (Enter 'quit' when you are finished.) quit
  ```

- 在循环中使用 continue

  要返回到循环开头，并根据条件测试结果决定是否继续执行循环，可使用 continue 语句，它不像 break 语句那样不再执行余下的代码并退出整个循环。例如，来看一个从 1 数到 10 ，但只打印其中偶数的循环

  ```python
  current_number = 0
  while current_number < 10:
      current_number += 1
      if current_number % 2 == 0:
          continue
      print(current_number)
      
  1
  3
  5
  7
  9
  ```

- 避免无限循环

  每个 while 循环都必须有停止运行的途径，这样才不会没完没了地执行下去

- 使用 while 循环来处理列表和字典

  for 循环是一种遍历列表的有效方式，但在 for 循环中不应修改列表，否则将导致 Python 难以跟踪其中的元素。要在遍历列表的同时对其进行修改，可使用 while 循环。通过将 while 循环同列表和字典结合起来使用，可收集、存储并组织大量输入，供以后查看和显示。

  在列表之间移动元素

  假设有一个列表，其中包含新注册但还未验证的网站用户；验证这些用户后，如何将他们移到另一个已验证用户列表中呢？一种办法是使用一个 while 循环，在验证用户的同时将其从未验证用户列表中提取出来，再将其加入到另一个已验证用户列表中。代码可能类似于下面这样

  ```python
  #  首先，创建一个待验证用户列表
  # 和一个用于存储已验证用户的空列表
  unconfirmed_users = ['alice', 'brian', 'candace']
  confirmed_users = []
  #  验证每个用户，直到没有未验证用户为止
  # 将每个经过验证的列表都移到已验证用户列表中
  while unconfirmed_users:
      current_user = unconfirmed_users.pop()
      print("Verifying user: " + current_user.title())
      confirmed_users.append(current_user)
  #  显示所有已验证的用户
  print("\nThe following users have been confirmed:")
  for confirmed_user in confirmed_users:
      print(confirmed_user.title())
      
  Verifying user: Candace
  Verifying user: Brian
  Verifying user: Alice
  
  The following users have been confirmed:
  Candace
  Brian
  Alice
  ```

- 删除包含特定值的所有列表元素

  假设你有一个宠物列表，其中包含多个值为 'cat' 的元素。要删除所有这些元素，可不断运行一个 while 循环，直到列表中不再包含值 'cat' ，如下所示

  ```python
  pets = ['dog', 'cat', 'dog', 'goldfish', 'cat', 'rabbit', 'cat']
  print(pets)
  while 'cat' in pets:
      pets.remove('cat')
  print(pets)
  
  ['dog', 'cat', 'dog', 'goldfish', 'cat', 'rabbit', 'cat']
  ['dog', 'dog', 'goldfish', 'rabbit']
  ```

- 使用用户输入来填充字典

  可使用 while 循环提示用户输入任意数量的信息。下面来创建一个调查程序，其中的循环每次执行时都提示输入被调查者的名字和回答。我们将收集的数据存储在一个字典中，以便将回答同被调查者关联起来

  ```python
  responses = {}
  # 设置一个标志，指出调查是否继续
  polling_active = True
  
  while polling_active:
      # 提示输入被调查者的名字和回答
      name = input("\nWhat is your name ? ")
      response = input("Which mountain would you like to climb sonmeday ? ")
  
      # 将答卷储存在字典中
      responses[name] = response
  
      #看看是否还有人要参与调查
      repeat = input("Would you like to let another person respond ? (yes/no) ")
      if repeat == 'no':
          polling_active = False
  
  # 调查结束，显示结果
  print("\n--- Poll Results ---")
  for name,response in responses.items():
      print(name + " would like to climb " + response + ".")
      
  What is your name ? mao
  Which mountain would you like to climb sonmeday ? huashan
  Would you like to let another person respond ? (yes/no) no
  
  --- Poll Results ---
  mao would like to climb huashan.
  ```
