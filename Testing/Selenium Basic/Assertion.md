### **3.1. _assertEquals_**[](https://www.baeldung.com/junit-assertions#junit4-assertequals)

The _assertEquals_ assertion verifies that the expected and actual values are equal:

```java
@Test
public void whenAssertingEquality_thenEqual() {
    String expected = "Baeldung";
    String actual = "Baeldung";

    assertEquals(expected, actual);
}
```

It's also possible to specify a message that displays when the assertion fails:

```java
assertEquals("failure - strings are not equal", expected, actual);
```

### **3.2. _assertArrayEquals_**[](https://www.baeldung.com/junit-assertions#junit4-assertArrayEquals)

If we want to assert that two arrays are equals, we can use the _assertArrayEquals:_

```java
@Test
public void whenAssertingArraysEquality_thenEqual() {
    char[] expected = {'J','u','n','i','t'};
    char[] actual = "Junit".toCharArray();
    
    assertArrayEquals(expected, actual);
}
```

If both arrays are _null_, the assertion will consider them equal:

```java
@Test
public void givenNullArrays_whenAssertingArraysEquality_thenEqual() {
    int[] expected = null;
    int[] actual = null;

    assertArrayEquals(expected, actual);
}
```

### **3.3. _assertNotNull_ and _assertNull_**[](https://www.baeldung.com/junit-assertions#junit4-null)

When we want to test if an object is _null,_ we can use the _assertNull_ assertion:

freestar.config.enabled\_slots.push({ placementName: "baeldung\_leaderboard\_mid\_3", slotId: "baeldung\_leaderboard\_mid\_3" });

```java
@Test
public void whenAssertingNull_thenTrue() {
    Object car = null;
    
    assertNull("The car should be null", car);
}
```

Conversely, if we want to assert that an object shouldn't be null, we can use the _assertNotNull_ assertion.

### **3.4. _assertNotSame_ and _assertSame_**[](https://www.baeldung.com/junit-assertions#junit4-same)

With _assertNotSame_, it's possible to verify that two variables don't refer to the same object:

```java
@Test
public void whenAssertingNotSameObject_thenDifferent() {
    Object cat = new Object();
    Object dog = new Object();

    assertNotSame(cat, dog);
}
```

Otherwise, when we want to verify that two variables do refer to the same object, we can use the _assertSame_ assertion.

### **3.5. _assertTrue_ and _assertFalse_**[](https://www.baeldung.com/junit-assertions#junit4-condition)

If we want to verify that a certain condition is _true_ or _false_, we can use the _assertTrue_ or _assertFalse_ assertions, respectively:

```java
@Test
public void whenAssertingConditions_thenVerified() {
    assertTrue("5 is greater then 4", 5 > 4);
    assertFalse("5 is not greater then 6", 5 > 6);
}
```

### **3.6.** **_fail_**[](https://www.baeldung.com/junit-assertions#junit4-fail)

The _fail_ assertion fails a test throwing an _AssertionFailedError_. It can be used to verify that an actual exception is thrown, or when we want to make a test fail during its development.

Let's see how we can use it in the first scenario:

```java
@Test
public void whenCheckingExceptionMessage_thenEqual() {
    try {
        methodThatShouldThrowException();
        fail("Exception not thrown");
    } catch (UnsupportedOperationException e) {
        assertEquals("Operation Not Supported", e.getMessage());
    }
}
```

### **3.7. _assertThat_**[](https://www.baeldung.com/junit-assertions#junit4-assertThat)

The _assertThat_ assertion is the only one in JUnit 4 that has a reverse order of parameters compared to the other assertions.

In this case, the assertion has an optional failure message, the actual value, and a _Matcher_ object.

freestar.config.enabled\_slots.push({ placementName: "baeldung\_incontent\_1", slotId: "baeldung\_incontent\_1" });

Let's see how we can use this assertion to check if an array contains particular values:

```java
@Test
public void testAssertThatHasItems() {
    assertThat(
      Arrays.asList("Java", "Kotlin", "Scala"), 
      hasItems("Java", "Kotlin"));
}
```

Additional information on the powerful use of the _assertThat_ assertion with the _Matcher_ object is available at [Testing with Hamcrest](https://www.baeldung.com/java-junit-hamcrest-guide).

## **4\. JUnit 5 Assertions**[](https://www.baeldung.com/junit-assertions#assertions-junit5)

JUnit 5 kept many of the assertion methods of JUnit 4, while adding a few new ones that take advantage of the Java 8 support.

Also, in this version of the library, assertions are available for all primitive types: _Objects,_ and arrays (either of primitives or Objects).

Notably, the order of the parameters of the assertions changed, moving the output message parameter to the last parameter. Thanks to the support of Java 8, the output message can be a _Supplier_, allowing lazy evaluation of it.

Let's start by reviewing the assertions that already had a JUnit 4 equivalent.

### **4.1. _assertArrayEquals_**[](https://www.baeldung.com/junit-assertions#junit5-assertArrayEquals)

The _assertArrayEquals_ assertion verifies that the expected and actual arrays are equal:

```java
@Test
public void whenAssertingArraysEquality_thenEqual() {
    char[] expected = { 'J', 'u', 'p', 'i', 't', 'e', 'r' };
    char[] actual = "Jupiter".toCharArray();

    assertArrayEquals(expected, actual, "Arrays should be equal");
}
```

If the arrays aren't equal, the message “_Arrays should be equal_” will be displayed as output.

freestar.config.enabled\_slots.push({ placementName: "baeldung\_incontent\_2", slotId: "baeldung\_incontent\_2" });

### **4.2. _assertEquals_**[](https://www.baeldung.com/junit-assertions#junit5-assertEquals)

If we want to assert that two _floats_ are equal, we can use the simple _assertEquals_ assertion:

```java
@Test
void whenAssertingEquality_thenEqual() {
    float square = 2 * 2;
    float rectangle = 2 * 2;

    assertEquals(square, rectangle);
}
```

However, if we want to assert that the actual value differs by a predefined delta from the expected value, we can still use the _assertEquals,_ but we have to pass the delta value as the third parameter:

```java
@Test
void whenAssertingEqualityWithDelta_thenEqual() {
    float square = 2 * 2;
    float rectangle = 3 * 2;
    float delta = 2;

    assertEquals(square, rectangle, delta);
}
```

### **4.3. _assertTrue_ and _assertFalse_**[](https://www.baeldung.com/junit-assertions#junit5-condition)

With the _assertTrue_ assertion, it's possible to verify the supplied conditions are _true_:

```java
@Test
void whenAssertingConditions_thenVerified() {
    assertTrue(5 > 4, "5 is greater the 4");
    assertTrue(null == null, "null is equal to null");
}
```

Thanks to the support of the lambda expression, it's possible to supply a _BooleanSupplier_ to the assertion, instead of a _boolean_ condition.

Let's see how we can assert the correctness of a _BooleanSupplier_ using the _assertFalse_ assertion:

```java
@Test
public void givenBooleanSupplier_whenAssertingCondition_thenVerified() {
    BooleanSupplier condition = () -> 5 > 6;

    assertFalse(condition, "5 is not greater then 6");
}
```

### **4.4. _assertNull_ and _assertNotNull_**[](https://www.baeldung.com/junit-assertions#junit5-null)

When we want to assert that an object is not _null,_ we can use the _assertNotNull_ assertion:

```java
@Test
void whenAssertingNotNull_thenTrue() {
    Object dog = new Object();

    assertNotNull(dog, () -> "The dog should not be null");
}
```

Conversely, we can use the _assertNull_ assertion to check if the actual is _null_:

```java
@Test
public void whenAssertingNull_thenTrue() {
    Object cat = null;

    assertNull(cat, () -> "The cat should be null");
}
```

In both cases, the failure message will be retrieved in a lazy way since it's a _Supplier_.

freestar.config.enabled\_slots.push({ placementName: "baeldung\_incontent\_3", slotId: "baeldung\_incontent\_3" });

### **4.5. _assertSame_ and _assertNotSame_**[](https://www.baeldung.com/junit-assertions#junit5-same)

When we want to assert that the expected and actual refer to the same _Object_, we must use the _assertSame_ assertion:

```java
@Test
void whenAssertingSameObject_thenSuccessfull() {
    String language = "Java";
    Optional<String> optional = Optional.of(language);

    assertSame(language, optional.get());
}
```

To achieve the opposite, we can use the _assertNotSame_ one.

### **4.6. _fail_**[](https://www.baeldung.com/junit-assertions#junit5-fail)

The _fail_ assertion fails a test with the provided failure message, as well as the underlying cause. This can be useful to mark a test when it's development isn't complete:

```java
@Test
public void whenFailingATest_thenFailed() {
    // Test not completed
    fail("FAIL - test not completed");
}
```

### **4.7. _assertAll_**[](https://www.baeldung.com/junit-assertions#junit5-assertAll)

One of the new assertions introduced in JUnit 5 is _assertAll_.

This assertion allows the creation of grouped assertions, where all the assertions are executed and their failures are reported together. In detail, this assertion accepts a heading that will be included in the message string for the _MultipleFailureError_, and a _Stream_ of _Executable._

Let's define a grouped assertion:

```java
@Test
void givenMultipleAssertion_whenAssertingAll_thenOK() {
    Object obj = null;
    assertAll(
      "heading",
      () -> assertEquals(4, 2 * 2, "4 is 2 times 2"),
      () -> assertEquals("java", "JAVA".toLowerCase()),
      () -> assertNull(obj, "obj is null")
    );
}
```

The execution of a grouped assertion is interrupted only when one of the executables throws a blacklisted exception (_OutOfMemoryError,_ for example).

### **4.8. _assertIterableEquals_**[](https://www.baeldung.com/junit-assertions#junit5-assertIterableEquals)

The _assertIterableEquals_ asserts that the expected and actual iterables are deeply equal.

freestar.config.enabled\_slots.push({ placementName: "baeldung\_incontent\_4", slotId: "baeldung\_incontent\_4" });

In order to be equal, both iterables must return equal elements in the same order, and it isn't required that the two iterables are of the same type in order to be equal.

With this consideration, let's see how we can assert that two lists of different types (_LinkedList_ and _ArrayList_) are equal:

```java
@Test
void givenTwoLists_whenAssertingIterables_thenEquals() {
    Iterable<String> al = new ArrayList<>(asList("Java", "Junit", "Test"));
    Iterable<String> ll = new LinkedList<>(asList("Java", "Junit", "Test"));

    assertIterableEquals(al, ll);
}
```

In the same way as _assertArrayEquals_, if both iterables are null, they're considered equal.

### **4.9. _assertLinesMatch_**[](https://www.baeldung.com/junit-assertions#junit5-assertLinesMatch)

The _assertLinesMatch_ asserts that the expected list of _String_ matches the actual list.

This method differs from the _assertEquals_ and _assertIterableEquals_ because for each pair of expected and actual lines, it performs this algorithm:

1.  Check if the expected line is equal to the actual one. If yes, it continues with the next pair.
2.  Treat the expected line as a regular expression and perform a check with the _String_._matches()_ method. If yes, it continues with the next pair.
3.  Check if the expected line is a fast-forward marker. If yes, apply fast-forward, and repeat the algorithm from the step 1.

Let's see how we can use this assertion to assert that two lists of _String_ have matching lines:

```java
@Test
void whenAssertingEqualityListOfStrings_thenEqual() {
    List<String> expected = asList("Java", "\\d+", "JUnit");
    List<String> actual = asList("Java", "11", "JUnit");

    assertLinesMatch(expected, actual);
}
```

### **4.10. _assertNotEquals_**[](https://www.baeldung.com/junit-assertions#junit5-assertNotEquals)

Complementary to _assertEquals_, the _assertNotEquals_ assertion asserts that the expected and actual values aren't equal:

```java
@Test
void whenAssertingEquality_thenNotEqual() {
    Integer value = 5; // result of an algorithm
    
    assertNotEquals(0, value, "The result cannot be 0");
}
```

If both are _null_, the assertion fails.

freestar.config.enabled\_slots.push({ placementName: "baeldung\_incontent\_5", slotId: "baeldung\_incontent\_5" });

### **4.11. _assertThrows_**[](https://www.baeldung.com/junit-assertions#junit5-assertThrows)

In order to increase simplicity and readability, the new _assertThrows_ assertion allows us a clear and simple way to assert if an executable throws the specified exception type.

Let's see how we can assert a thrown exception:

```java
@Test
void whenAssertingException_thenThrown() {
    Throwable exception = assertThrows(
      IllegalArgumentException.class, 
      () -> {
          throw new IllegalArgumentException("Exception message");
      }
    );
    assertEquals("Exception message", exception.getMessage());
}
```

The assertion will fail if no exception is thrown, or if an exception of a different type is thrown.

### **4.12. _assertTimeout_ and _assertTimeoutPreemptively_**[](https://www.baeldung.com/junit-assertions#junit5-timeout)

If we want to assert that the execution of a supplied _Executable_ ends before a given _Timeout_, we can use the _assertTimeout_ assertion:

```java
@Test
void whenAssertingTimeout_thenNotExceeded() {
    assertTimeout(
      ofSeconds(2), 
      () -> {
        // code that requires less than 2 minutes to execute
        Thread.sleep(1000);
      }
    );
}
```