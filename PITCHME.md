# PHP Exception Classes and usage

- What are Exceptions?

+ Definition: An exception is an event, which occurs during the execution of a program, that disrupts the normal flow of the program's instructions. 

---

+ Example: 
	+ Memory leak
	+ trying to get a nonexisitng object
	+ Duplicate primary key 

---

- What is Exception handling?

+ Exception handling is the process of responding to the occurrence, during computation, of exceptions – anomalous or exceptional conditions requiring special processing – often changing the normal flow of program execution. 
+ It is provided by specialized programming language constructs, computer hardware mechanisms like interrupts or operating system IPC facilities like signals.

---

+ Exceptions need to be handled gracefully.

---

+ In general, an exception breaks the normal flow of execution and executes a pre-registered exception handler. 
+ The details of how this is done depends on whether it is a hardware or software exception and how the software exception is implemented. 
+ Some exceptions, especially hardware ones, may be handled so gracefully that execution can resume where it was interrupted.

---

## PHP Exception class

Predefined Exception and The SPL Exception class

- http://php.net/manual/en/reserved.exceptions.php
- http://php.net/manual/en/spl.exceptions.php

---

+ LogicException (extends Exception)
  + BadFunctionCallException
    + BadMethodCallException
  + DomainException
  + InvalidArgumentException
  + LengthException
  + OutOfRangeException

---

+ RuntimeException (extends Exception)
  + OutOfBoundsException
  + OverflowException
  + RangeException
  + UnderflowException
  + UnexpectedValueException

---

## Custom Exception class

+ PDOException
  + EdanzDatabaseException

+ EdanzException
  + EdanzPaymentException
    + EdanzPaypalPaymentException
    + EdanzSMBCPaymentException
+ EdanzBackboneAPIException
    + EdanzR2BackboneAPIException
    + EdanzS2BackboneAPIException

---

## try .. catch

```
<?php
function inverse($x) {
    if (!$x) {
        throw new Exception('Division by zero.');
    }
    return 1/$x;
}

try {
    echo inverse(5) . "\n";
    echo inverse(0) . "\n";
} catch (Exception $e) {
    echo 'Caught exception: ',  $e->getMessage(), "\n";
}

// Continue execution
echo "Hello World\n";
?>
```

---

## catch .. finally

```
<?php
function inverse($x) {
    if (!$x) {
        throw new Exception('Division by zero.');
    }
    return 1/$x;
}

try {
    echo inverse(5) . "\n";
} catch (Exception $e) {
    echo 'Caught exception: ',  $e->getMessage(), "\n";
} finally {
    echo "First finally.\n";
}
```
---
```
<?php
try {
    echo inverse(0) . "\n";
} catch (Exception $e) {
    echo 'Caught exception: ',  $e->getMessage(), "\n";
} finally {
    echo "Second finally.\n";
}

// Continue execution
echo "Hello World\n";
```

---

## catch .. catch

```
  try {
    $variables = get_backbone_jobs_table($uid);
  }
  catch (EdanzException $e) {
    $e->handle();
  }
  catch (Exception $e) {
    watchdog('backbone', $e->getMessage(), WATCHDOG_ERROR);
  }
```

---

## Example

```
$txn = db_transaction();
try {
    $id = db_insert('example')
      ->fields(array(
        'field1' => 'mystring',
        'field2' => 5,
      ))
      ->execute();

    my_other_function($id);

    return $id;
  }
  catch (Exception $e) {
    // Something went wrong somewhere, so roll back now.
    $txn->rollback();
    // Log the exception to watchdog.
    watchdog_exception('type', $e);
  }
```

---

## ProjectX Exception handling

+ Backbone API calls
+ Payments
+ Database calls
+ ...
+ ...

