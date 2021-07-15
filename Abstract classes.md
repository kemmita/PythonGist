```py
from abc import abstractmethod


class Printer:
    @abstractmethod
    def print(self, document):
        pass


class Fax:
    def __init__(self):
        self.__current_time = '12:00 AM'

    @abstractmethod
    def fax(self, document):
        pass

    def inf_on_fax(self):
        print(f'current time: {self.__current_time}')


class Scan:
    @abstractmethod
    def scan(self, document):
        pass


class MultifunctionPrinter(Printer, Fax, Scan):
    def scan(self, document):
        print('Concrete implementation of scan')

    def print(self, document):
        print('Concrete implementation of print')

    def fax(self, document):
        print('Concrete implementation of fax')


class OldFashionedPrinter(Printer):
    def print(self, document):
        print('Concrete implementation')


modern_printer = MultifunctionPrinter()
modern_printer.fax('document to work with')
modern_printer.inf_on_fax()
```
