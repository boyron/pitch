# PHP Exception Classes and usage

- What are Exceptions?

Definition: An exception is an event, which occurs during the execution of a program, that disrupts the normal flow of the program's instructions. 
Example: Let's think of some.

---

- What is Exception handling?

Exception handling is the process of responding to the occurrence, during computation, of exceptions – anomalous or exceptional conditions requiring special processing – often changing the normal flow of program execution. It is provided by specialized programming language constructs, computer hardware mechanisms like interrupts or operating system IPC facilities like signals.

Exceptions need to be handled gracefully.

---

In general, an exception breaks the normal flow of execution and executes a pre-registered exception handler. 
The details of how this is done depends on whether it is a hardware or software exception and how the software exception is implemented. 
Some exceptions, especially hardware ones, may be handled so gracefully that execution can resume where it was interrupted.

---

## PHP Exception class

Predefined Exception and The SPL Exception class

- http://php.net/manual/en/reserved.exceptions.php
- http://php.net/manual/en/spl.exceptions.php

---

LogicException (extends Exception)
  BadFunctionCallException
    BadMethodCallException
  DomainException
  InvalidArgumentException
  LengthException
  OutOfRangeException
RuntimeException (extends Exception)
  OutOfBoundsException
  OverflowException
  RangeException
  UnderflowException
  UnexpectedValueException

---

