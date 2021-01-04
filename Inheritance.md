```py
class Device:
    def __init__(self, name, connected_by):
        self.name = name
        self.connected_by = connected_by
        self.connected = True

    def disconnect(self):
        self.connected = False
        print(f"{self.name} disconnected.")

# Here we inherit from the Deivce class and use super to call the base class constructor.
class Printer(Device):
    def __init__(self, name, connected_by, capacity):
        super().__init__(name, connected_by)
        self.capacity = capacity

    def print(self, number_of_pages):
        if number_of_pages > self.capacity:
            return f'The current capacity, {self.capacity} ' \
                   f'is not able to fulfil your request of {number_of_pages} pages.'
        print(f'Printing {number_of_pages} pages...')


printer = Printer('Xon', 'USB', 200)
print(printer.print(100))
printer.disconnect()
```
