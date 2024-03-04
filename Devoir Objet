class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class MyOutOfSizeException(Exception):
    pass

class MyEmptyStackException(Exception):
    pass

class MyStack:
    def __init__(self, max_size):
        self.max_size = max_size
        self.size = 0
        self.top = None

    def add_to_stack(self, element):
        if self.size < self.max_size:
            new_node = Node(element)
            new_node.next = self.top
            self.top = new_node
            self.size += 1
        else:
            raise MyOutOfSizeException("MyStack is full")

    def pop_from_stack(self):
        if self.is_empty():
            raise MyEmptyStackException("MyStack is empty")
        data = self.top.data
        self.top = self.top.next
        self.size -= 1
        return data

    def is_empty(self):
        return self.size == 0

    def is_full(self):
        return self.size == self.max_size


if __name__ == '__main__':
    myStack = MyStack(3)
    myStack.add_to_stack('hello')
    myStack.add_to_stack('world')
    print(myStack.is_full())  # False
    myStack.add_to_stack('python')
    print(myStack.is_full())  # True

    try:
        myStack.add_to_stack('error')  # MyOutOfSizeException
    except MyOutOfSizeException as e:
        print(e)

    print(myStack.pop_from_stack())  # python
    print(myStack.is_empty())  # False
    print(myStack.pop_from_stack())  # world
    print(myStack.is_empty())  # False
    print(myStack.pop_from_stack())  # hello
    print(myStack.is_empty())  # True

    try:
        print(myStack.pop_from_stack())  # MyEmptyStackException
    except MyEmptyStackException as e:
        print(e)
