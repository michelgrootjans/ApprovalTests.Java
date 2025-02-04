<a id="top"></a>

# Features

<!-- toc -->
## Contents

  * [toArray](#toarray)
  * [Queryable and Extendable](#queryable-and-extendable)
  * [Functions](#functions)
  * [Actions](#actions)
  * [Actions.doNothing()](#actionsdonothing)
  * [SimpleLogger.logToNothing()](#simpleloggerlogtonothing)
  * [NullLogger](#nulllogger)
  * [ArrayUtils.addToArray()](#arrayutilsaddtoarray)<!-- endToc -->

## toArray
see [ArrayUtils.toArray](ArrayUtils.md#toArray) 
## Queryable and Extendable
see [Query](Queryable.md#top) a group of map-reduce functions based on the linq (sql) syntax.

## Functions

Function0 through Function9 are single method interfaces for use with lambdas where you take 0-9 parameters and return a result.  
For Example Function3 has the single method :

<!-- snippet: function3_call -->
<a id='snippet-function3_call'></a>
```java
public Out call(In1 a, In2 b, In3 c);
```
<sup><a href='/approvaltests-util/src/main/java/org/lambda/functions/Function3.java#L5-L7' title='Snippet source file'>snippet source</a> | <a href='#snippet-function3_call' title='Start of snippet'>anchor</a></sup>
<!-- endSnippet -->

The first 3 have native java equivalents (that are hard to remember).  
If it is preferred to use those, but can't remember their name, they are listed in the javadocs.  

```
   Function0 -> java.util.function.Supplier  
   Function1 -> java.util.function.Function  
   Function2 -> java.util.function.BiFunction
```
## Actions

Action0 through Action9 are single method interfaces for use with lambdas where you take 0-9 parameters and all results are via side-effect (void return).


For Example Action3 has the single method:  

<!-- snippet: action3_call -->
<a id='snippet-action3_call'></a>
```java
public void call(In1 a, In2 b, In3 c);
```
<sup><a href='/approvaltests-util/src/main/java/org/lambda/actions/Action3.java#L10-L12' title='Snippet source file'>snippet source</a> | <a href='#snippet-action3_call' title='Start of snippet'>anchor</a></sup>
<!-- endSnippet -->

The first 3 have native java equivalents (that are hard to remember).  
If it is preferred to use those, but can't remember their name, they are listed in the javadocs.      

```
   Action0 -> java.lang.Runnable  
   Action1 -> java.util.function.Consumer  
   Action2 -> java.util.function.BiConsumer
```

## Actions.doNothing()

Action0 thru Action9 all have an implementation of the null object pattern for your convenience.


## SimpleLogger.logToNothing()

SimpleLogger is used to make approvaltesting easier, but approvalTests also uses it internally. Something these bleed out in the form of messages like

<!-- snippet: /approvaltests-util-tests/src/test/java/com/spun/util/logger/SimpleLoggerTest.test.approved.txt -->
<a id='snippet-/approvaltests-util-tests/src/test/java/com/spun/util/logger/SimpleLoggerTest.test.approved.txt'></a>
```txt
=> SimpleLoggerTest.test() - IN
   => SimpleLoggerTest.test() - IN
      Event: Starting Logging
      Variable: name = 'llewellyn'
      Sql: Select * from people
      .........1.........2.........3.........4..
      Variable: Numbers.length = 5
      Numbers[0] = 1
      Numbers[1] = 2
      Numbers[2] = 3
      Numbers[3] = 4
      Numbers[4] = 5
******************************************************************************************
      
java.lang.Error -  null
******************************************************************************************
   <= SimpleLoggerTest.test() - OUT
<= SimpleLoggerTest.test() - OUT
```
<sup><a href='/approvaltests-util-tests/src/test/java/com/spun/util/logger/SimpleLoggerTest.test.approved.txt#L1-L18' title='Snippet source file'>snippet source</a> | <a href='#snippet-/approvaltests-util-tests/src/test/java/com/spun/util/logger/SimpleLoggerTest.test.approved.txt' title='Start of snippet'>anchor</a></sup>
<!-- endSnippet -->

if you want to turn them all off just run

<!-- snippet: log_nothing -->
<a id='snippet-log_nothing'></a>
```java
SimpleLogger.logToNothing();
```
<sup><a href='/approvaltests-util-tests/src/test/java/com/spun/util/logger/SimpleLoggerTest.java#L32-L34' title='Snippet source file'>snippet source</a> | <a href='#snippet-log_nothing' title='Start of snippet'>anchor</a></sup>
<!-- endSnippet -->

## NullLogger

Null Object Pattern for java.lang.Appendable

## ArrayUtils.addToArray()

Sometimes you wish you could add to an array the same way you can add to a list.
<!-- snippet: add_to_array -->
<a id='snippet-add_to_array'></a>
```java
Integer[] numbers = {1, 2, 3};
numbers = ArrayUtils.addToArray(numbers, 4, 5, 6);
```
<sup><a href='/approvaltests-util-tests/src/test/java/com/spun/util/ArrayUtilsTest.java#L18-L21' title='Snippet source file'>snippet source</a> | <a href='#snippet-add_to_array' title='Start of snippet'>anchor</a></sup>
<!-- endSnippet -->

will result in a new copy of the array with the added items
<!-- snippet: add_to_array_result -->
<a id='snippet-add_to_array_result'></a>
```java
Integer[] resulting = {1, 2, 3, 4, 5, 6};
```
<sup><a href='/approvaltests-util-tests/src/test/java/com/spun/util/ArrayUtilsTest.java#L22-L24' title='Snippet source file'>snippet source</a> | <a href='#snippet-add_to_array_result' title='Start of snippet'>anchor</a></sup>
<!-- endSnippet -->

[Back to User Guide](README.md#top)
