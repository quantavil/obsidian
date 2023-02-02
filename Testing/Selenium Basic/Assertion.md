- [[#assertEquals|assertEquals]]
- [[#assertArrayEquals|assertArrayEquals]]
- [[#assertNotNull and assertNull|assertNotNull and assertNull]]
- [[#assertNotSame and assertSame|assertNotSame and assertSame]]
- [[#assertTrue and assertFalse|assertTrue and assertFalse]]
- [[#fail|fail]]
- [[#assertThat|assertThat]]

## assertEquals

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

## assertArrayEquals
If we want to assert that two arrays are equals, we can use the _assertArrayEquals:_

```java
@Test
public void whenAssertingArraysEquality_thenEqual() {
    char[] expected = {'J','u','n','i','t'};
    char[] actual = "Junit".toCharArray();
    
    assertArrayEquals(expected, actual);
}
```


## assertNotNull and assertNull

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

## assertNotSame and assertSame

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

## assertTrue and assertFalse
If we want to verify that a certain condition is _true_ or _false_, we can use the _assertTrue_ or _assertFalse_ assertions, respectively:

```java
@Test
public void whenAssertingConditions_thenVerified() {
    assertTrue("5 is greater then 4", 5 > 4);
    assertFalse("5 is not greater then 6", 5 > 6);
}
```

## fail

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

## assertThat

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

