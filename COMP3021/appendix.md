## Appendix A: Java 12 and JavaFX 12 API Documentation

### `java.util.ArrayList<E>`

```java
package java.util;

/**
 * Resizable-array implementation of the {@code List} interface.  Implements
 * all optional list operations, and permits all elements, including
 * {@code null}.  In addition to implementing the {@code List} interface,
 * this class provides methods to manipulate the size of the array that is
 * used internally to store the list.
 *
 * @param <E> the type of elements in this list
 */
public class ArrayList<E> extends AbstractList<E>
        implements List<E>, RandomAccess, Cloneable, java.io.Serializable {
    /**
     * Constructs an empty list with an initial capacity of ten.
     */
    public ArrayList();

    /**
     * Appends the specified element to the end of this list.
     *
     * @param e element to be appended to this list
     * @return {@code true} (as specified by {@link Collection#add})
     */
    public boolean add(E e);

    /**
     * Inserts the specified element at the specified position in this
     * list. Shifts the element currently at that position (if any) and
     * any subsequent elements to the right (adds one to their indices).
     *
     * @param index index at which the specified element is to be inserted
     * @param element element to be inserted
     * @throws IndexOutOfBoundsException {@inheritDoc}
     */
    public void add(int index, E element);

    /**
     * Removes all of the elements from this list.  The list will
     * be empty after this call returns.
     */
    public void clear();

    /**
     * Returns {@code true} if this list contains the specified element.
     *
     * @param o element whose presence in this list is to be tested
     * @return {@code true} if this list contains the specified element
     */
    public boolean contains(Object o);

    /**
     * Returns the element at the specified position in this list.
     *
     * @param  index index of the element to return
     * @return the element at the specified position in this list
     * @throws IndexOutOfBoundsException {@inheritDoc}
     */
    public E get(int index);

    /**
     * Returns the index of the first occurrence of the specified element
     * in this list, or -1 if this list does not contain the element.
     */
    public int indexOf(Object o);

    /**
     * Returns {@code true} if this list contains no elements.
     *
     * @return {@code true} if this list contains no elements
     */
    public boolean isEmpty();

    /**
     * Returns the index of the last occurrence of the specified element
     * in this list, or -1 if this list does not contain the element.
     */
    public int lastIndexOf(Object o);

    /**
     * Removes the first occurrence of the specified element from this list,
     * if it is present.  If the list does not contain the element, it is
     * unchanged.
     *
     * @param o element to be removed from this list, if present
     * @return {@code true} if this list contained the specified element
     */
    public boolean remove(Object o);

    /**
     * Returns the number of elements in this list.
     *
     * @return the number of elements in this list
     */
    public int size();

    /**
     * Removes the first occurrence of the specified element from this list,
     * if it is present.  If the list does not contain the element, it is
     * unchanged.
     *
     * @param o element to be removed from this list, if present
     * @return {@code true} if this list contained the specified element
     */
    public boolean remove(Object o);

    /**
     * Replaces the element at the specified position in this list with
     * the specified element.
     *
     * @param index index of the element to replace
     * @param element element to be stored at the specified position
     * @return the element previously at the specified position
     * @throws IndexOutOfBoundsException {@inheritDoc}
     */
    public E set(int index, E element);

    /**
     * Returns an array containing all of the elements in this list in proper
     * sequence (from first to last element); the runtime type of the returned
     * array is that of the specified array.  If the list fits in the
     * specified array, it is returned therein.  Otherwise, a new array is
     * allocated with the runtime type of the specified array and the size of
     * this list.
     *
     * <p>If the list fits in the specified array with room to spare
     * (i.e., the array has more elements than the list), the element in
     * the array immediately following the end of the collection is set to
     * {@code null}.
     *
     * @param a the array into which the elements of the list are to
     *          be stored, if it is big enough; otherwise, a new array of the
     *          same runtime type is allocated for this purpose.
     * @return an array containing the elements of the list
     * @throws ArrayStoreException if the runtime type of the specified array
     *         is not a supertype of the runtime type of every element in
     *         this list
     * @throws NullPointerException if the specified array is null
     */
    @SuppressWarnings("unchecked")
    public <T> T[] toArray(T[] a);

    /**
     * Returns a sequential {@code Stream} with this collection as its source.
     *
     * @return a sequential {@code Stream} over the elements in this collection
     */
    default Stream<E> stream();

    /**
     * Returns a possibly parallel {@code Stream} with this collection as its
     * source.  It is allowable for this method to return a sequential stream.
     *
     * @return a possibly parallel {@code Stream} over the elements in this
     * collection
     */
    default Stream<E> parallelStream();
}
```

### `java.util.Arrays`

```java
package java.util;

/**
 * This class contains various methods for manipulating arrays (such as
 * sorting and searching). This class also contains a static factory
 * that allows arrays to be viewed as lists.
 *
 * <p>The methods in this class all throw a {@code NullPointerException},
 * if the specified array reference is null, except where noted.
 */
public class Arrays {
    /**
     * Returns a fixed-size list backed by the specified array. Changes made to
     * the array will be visible in the returned list, and changes made to the
     * list will be visible in the array.
     *
     * @param <T> the class of the objects in the array
     * @param a the array by which the list will be backed
     * @return a list view of the specified array
     * @throws NullPointerException if the specified array is {@code null}
     */
    @SafeVarargs
    @SuppressWarnings("varargs")
    public static <T> List<T> asList(T... a);
}
```

### `java.lang.String`

```java
package java.lang;

/**
 * The {@code String} class represents character strings. All
 * string literals in Java programs, such as {@code "abc"}, are
 * implemented as instances of this class.
 * <p>
 * Strings are constant; their values cannot be changed after they
 * are created. String buffers support mutable strings.
 *
 * <p> Unless otherwise noted, passing a {@code null} argument to a constructor
 * or method in this class will cause a {@link NullPointerException} to be
 * thrown.
 */
public final class String
    implements java.io.Serializable, Comparable<String>, CharSequence {
    /**
     * Initializes a newly created {@code String} object so that it represents
     * an empty character sequence.
     */
    public String();

    /**
     * Initializes a newly created {@code String} object so that it represents
     * the same sequence of characters as the argument; in other words, the
     * newly created string is a copy of the argument string.
     *
     * @param  original
     *         A {@code String}
     */
    @HotSpotIntrinsicCandidate
    public String(String original);

    /**
     * Compares this string to the specified object.  The result is {@code
     * true} if and only if the argument is not {@code null} and is a {@code
     * String} object that represents the same sequence of characters as this
     * object.
     *
     * @param  anObject
     *         The object to compare this {@code String} against
     *
     * @return  {@code true} if the given object represents a {@code String}
     *          equivalent to this string, {@code false} otherwise
     */
    public boolean equals(Object anObject);

    /**
     * Compares two strings lexicographically.
     *
     * @param   anotherString   the {@code String} to be compared.
     * @return  the value {@code 0} if the argument string is equal to
     *          this string; a value less than {@code 0} if this string
     *          is lexicographically less than the string argument; and a
     *          value greater than {@code 0} if this string is
     *          lexicographically greater than the string argument.
     */
    public int compareTo(String anotherString);

    /**
     * Tests if this string starts with the specified prefix.
     *
     * @param   prefix   the prefix.
     * @return  {@code true} if the character sequence represented by the
     *          argument is a prefix of the character sequence represented by
     *          this string; {@code false} otherwise.
     *          Note also that {@code true} will be returned if the
     *          argument is an empty string or is equal to this
     *          {@code String} object as determined by the
     *          {@link #equals(Object)} method.
     */
    public boolean startsWith(String prefix);

    /**
     * Tests if this string ends with the specified suffix.
     *
     * @param   suffix   the suffix.
     * @return  {@code true} if the character sequence represented by the
     *          argument is a suffix of the character sequence represented by
     *          this object; {@code false} otherwise. Note that the
     *          result will be {@code true} if the argument is the
     *          empty string or is equal to this {@code String} object
     *          as determined by the {@link #equals(Object)} method.
     */
    public boolean endsWith(String suffix);

    /**
     * Compares this string to the specified object.  The result is {@code
     * true} if and only if the argument is not {@code null} and is a {@code
     * String} object that represents the same sequence of characters as this
     * object.
     *
     * @param  anObject
     *         The object to compare this {@code String} against
     *
     * @return  {@code true} if the given object represents a {@code String}
     *          equivalent to this string, {@code false} otherwise
     */
    public boolean equals(Object anObject);

    /**
     * Returns the length of this string.
     *
     * @return  the length of the sequence of characters represented by this
     *          object.
     */
    public int length();

    /**
     * Returns the {@code char} value at the
     * specified index. An index ranges from {@code 0} to
     * {@code length() - 1}. The first {@code char} value of the sequence
     * is at index {@code 0}, the next at index {@code 1},
     * and so on, as for array indexing.
     *
     * @param      index   the index of the {@code char} value.
     * @return     the {@code char} value at the specified index of this string.
     *             The first {@code char} value is at index {@code 0}.
     * @exception  IndexOutOfBoundsException  if the {@code index}
     *             argument is negative or not less than the length of this
     *             string.
     */
    public char charAt(int index);

    /**
     * Concatenates the specified string to the end of this string.
     *
     * @param   str   the {@code String} that is concatenated to the end
     *                of this {@code String}.
     * @return  a string that represents the concatenation of this object's
     *          characters followed by the string argument's characters.
     */
    public String concat(String str);

    /**
     * Returns a string that is a substring of this string. The
     * substring begins with the character at the specified index and
     * extends to the end of this string.
     *
     * @param      beginIndex   the beginning index, inclusive.
     * @return     the specified substring.
     * @exception  IndexOutOfBoundsException  if
     *             {@code beginIndex} is negative or larger than the
     *             length of this {@code String} object.
     */
    public String substring(int beginIndex);

    /**
     * Returns a string that is a substring of this string. The
     * substring begins at the specified {@code beginIndex} and
     * extends to the character at index {@code endIndex - 1}.
     * Thus the length of the substring is {@code endIndex-beginIndex}.
     *
     * @param      beginIndex   the beginning index, inclusive.
     * @param      endIndex     the ending index, exclusive.
     * @return     the specified substring.
     * @exception  IndexOutOfBoundsException  if the
     *             {@code beginIndex} is negative, or
     *             {@code endIndex} is larger than the length of
     *             this {@code String} object, or
     *             {@code beginIndex} is larger than
     *             {@code endIndex}.
     */
    public String substring(int beginIndex, int endIndex);

    /**
     * Converts all of the characters in this {@code String} to lower
     * case using the rules of the default locale. This is equivalent to calling
     * {@code toLowerCase(Locale.getDefault())}.
     *
     * @return  the {@code String}, converted to lowercase.
     */
    public String toLowerCase();

    /**
     * Converts all of the characters in this {@code String} to upper
     * case using the rules of the default locale. This method is equivalent to
     * {@code toUpperCase(Locale.getDefault())}.
     *
     * @return  the {@code String}, converted to uppercase.
     */
    public String toUpperCase();

    /**
     * Returns a string whose value is this string, with all leading
     * and trailing space removed.
     *
     * @return  a string whose value is this string, with all leading
     *          and trailing space removed, or this string if it
     *          has no leading or trailing space.
     */
    public String trim();

    /**
     * Returns a string resulting from replacing all occurrences of
     * {@code oldChar} in this string with {@code newChar}.
     *
     * @param   oldChar   the old character.
     * @param   newChar   the new character.
     * @return  a string derived from this string by replacing every
     *          occurrence of {@code oldChar} with {@code newChar}.
     */
    public String replace(char oldChar, char newChar);

    /**
     * Replaces the first substring of this string that matches the given <a
     * href="../util/regex/Pattern.html#sum">regular expression</a> with the
     * given replacement.
     *
     * @param   regex
     *          the regular expression to which this string is to be matched
     * @param   replacement
     *          the string to be substituted for the first match
     *
     * @return  The resulting {@code String}
     *
     * @throws  PatternSyntaxException
     *          if the regular expression's syntax is invalid
     */
    public String replaceFirst(String regex, String replacement);

    /**
     * Replaces each substring of this string that matches the given <a
     * href="../util/regex/Pattern.html#sum">regular expression</a> with the
     * given replacement.
     *
     * @param   regex
     *          the regular expression to which this string is to be matched
     * @param   replacement
     *          the string to be substituted for each match
     *
     * @return  The resulting {@code String}
     *
     * @throws  PatternSyntaxException
     *          if the regular expression's syntax is invalid
     */
    public String replaceAll(String regex, String replacement);

    /**
     * Splits this string around matches of the given <a
     * href="../util/regex/Pattern.html#sum">regular expression</a>.
     *
     *
     * @param  regex
     *         the delimiting regular expression
     *
     * @return  the array of strings computed by splitting this string
     *          around matches of the given regular expression
     *
     * @throws  PatternSyntaxException
     *          if the regular expression's syntax is invalid
     */
    public String[] split(String regex);

    /**
     * Returns the index within this string of the first occurrence of
     * the specified character.
     *
     * @param   ch   a character (Unicode code point).
     * @return  the index of the first occurrence of the character in the
     *          character sequence represented by this object, or
     *          {@code -1} if the character does not occur.
     */
    public int indexOf(int ch);

    /**
     * Returns the index within this string of the first occurrence of the
     * specified character, starting the search at the specified index.
     * <p>
     * There is no restriction on the value of {@code fromIndex}. If it
     * is negative, it has the same effect as if it were zero: this entire
     * string may be searched. If it is greater than the length of this
     * string, it has the same effect as if it were equal to the length of
     * this string: {@code -1} is returned.
     *
     * @param   ch          a character (Unicode code point).
     * @param   fromIndex   the index to start the search from.
     * @return  the index of the first occurrence of the character in the
     *          character sequence represented by this object that is greater
     *          than or equal to {@code fromIndex}, or {@code -1}
     *          if the character does not occur.
     */
    public int indexOf(int ch, int fromIndex);

    /**
     * Returns the index within this string of the first occurrence of the
     * specified substring.
     *
     * @param   str   the substring to search for.
     * @return  the index of the first occurrence of the specified substring,
     *          or {@code -1} if there is no such occurrence.
     */
    public int indexOf(String str);

    /**
     * Returns the index within this string of the first occurrence of the
     * specified substring, starting at the specified index.
     *
     * <p>The returned index is the smallest value {@code k} for which:
     * <pre>{@code
     *     k >= Math.min(fromIndex, this.length()) &&
     *                   this.startsWith(str, k)
     * }</pre>
     * If no such value of {@code k} exists, then {@code -1} is returned.
     *
     * @param   str         the substring to search for.
     * @param   fromIndex   the index from which to start the search.
     * @return  the index of the first occurrence of the specified substring,
     *          starting at the specified index,
     *          or {@code -1} if there is no such occurrence.
     */
    public int indexOf(String str, int fromIndex);

    /**
     * Returns the string representation of the {@code double} argument.
     * <p>
     * The representation is exactly the one returned by the
     * {@code Double.toString} method of one argument.
     *
     * @param   d   a {@code double}.
     * @return  a  string representation of the {@code double} argument.
     * @see     java.lang.Double#toString(double)
     */
    public static String valueOf(double d);
    // valueOf(...) primitive overloads

    /**
     * Returns a formatted string using the specified format string and
     * arguments.
     *
     * @param  format
     *         A <a href="../util/Formatter.html#syntax">format string</a>
     *
     * @param  args
     *         Arguments referenced by the format specifiers in the format
     *         string.  If there are more arguments than format specifiers, the
     *         extra arguments are ignored.  The number of arguments is
     *         variable and may be zero.
     *
     * @throws  java.util.IllegalFormatException
     *          If a format string contains an illegal syntax, a format
     *          specifier that is incompatible with the given arguments,
     *          insufficient arguments given the format string, or other
     *          illegal conditions.
     *
     * @return  A formatted string
     */
    public static String format(String format, Object... args);
}
```

### `java.lang.Object`

```java
package java.lang;

/**
 * Class {@code Object} is the root of the class hierarchy.
 * Every class has {@code Object} as a superclass. All objects,
 * including arrays, implement the methods of this class.
 */
public class Object {
    /**
     * Indicates whether some other object is "equal to" this one.
     *
     * @param   obj   the reference object with which to compare.
     * @return  {@code true} if this object is the same as the obj
     *          argument; {@code false} otherwise.
     */
    public boolean equals(Object obj);

    /**
     * Returns a hash code value for the object.
     *
     * @return  a hash code value for this object.
     */
    @HotSpotIntrinsicCandidate
    public native int hashCode();

    /**
     * Returns a string representation of the object.
     *
     * @return  a string representation of the object.
     */
    public String toString();

    /**
     * Creates and returns a copy of this object.  The precise meaning
     * of "copy" may depend on the class of the object.
     * <p>
     * The method {@code clone} for class {@code Object} performs a
     * specific cloning operation. First, if the class of this object does
     * not implement the interface {@code Cloneable}, then a
     * {@code CloneNotSupportedException} is thrown. Note that all arrays
     * are considered to implement the interface {@code Cloneable} and that
     * the return type of the {@code clone} method of an array type {@code T[]}
     * is {@code T[]} where T is any reference or primitive type.
     * Otherwise, this method creates a new instance of the class of this
     * object and initializes all its fields with exactly the contents of
     * the corresponding fields of this object, as if by assignment; the
     * contents of the fields are not themselves cloned. Thus, this method
     * performs a "shallow copy" of this object, not a "deep copy" operation.
     * <p>
     * The class {@code Object} does not itself implement the interface
     * {@code Cloneable}, so calling the {@code clone} method on an object
     * whose class is {@code Object} will result in throwing an
     * exception at run time.
     *
     * @return     a clone of this instance.
     * @throws  CloneNotSupportedException  if the object's class does not
     *               support the {@code Cloneable} interface. Subclasses
     *               that override the {@code clone} method can also
     *               throw this exception to indicate that an instance cannot
     *               be cloned.
     */
    @HotSpotIntrinsicCandidate
    protected native Object clone() throws CloneNotSupportedException;

    /**
     * Causes the current thread to wait until it is awakened, typically
     * by being <em>notified</em> or <em>interrupted</em>.
     *
     * @throws IllegalMonitorStateException if the current thread is not
     *         the owner of the object's monitor
     * @throws InterruptedException if any thread interrupted the current thread before or
     *         while the current thread was waiting. The <em>interrupted status</em> of the
     *         current thread is cleared when this exception is thrown.
     */
    public final void wait() throws InterruptedException;

    /**
     * Wakes up a single thread that is waiting on this object's
     * monitor. If any threads are waiting on this object, one of them
     * is chosen to be awakened. The choice is arbitrary and occurs at
     * the discretion of the implementation. A thread waits on an object's
     * monitor by calling one of the {@code wait} methods.
     * <p>
     * The awakened thread will not be able to proceed until the current
     * thread relinquishes the lock on this object. The awakened thread will
     * compete in the usual manner with any other threads that might be
     * actively competing to synchronize on this object; for example, the
     * awakened thread enjoys no reliable privilege or disadvantage in being
     * the next thread to lock this object.
     * <p>
     * This method should only be called by a thread that is the owner
     * of this object's monitor. A thread becomes the owner of the
     * object's monitor in one of three ways:
     * <ul>
     * <li>By executing a synchronized instance method of that object.
     * <li>By executing the body of a {@code synchronized} statement
     *     that synchronizes on the object.
     * <li>For objects of type {@code Class,} by executing a
     *     synchronized static method of that class.
     * </ul>
     * <p>
     * Only one thread at a time can own an object's monitor.
     *
     * @throws  IllegalMonitorStateException  if the current thread is not
     *               the owner of this object's monitor.
     */
    @HotSpotIntrinsicCandidate
    public final native void notify();

    /**
     * Wakes up all threads that are waiting on this object's monitor. A
     * thread waits on an object's monitor by calling one of the
     * {@code wait} methods.
     * <p>
     * The awakened threads will not be able to proceed until the current
     * thread relinquishes the lock on this object. The awakened threads
     * will compete in the usual manner with any other threads that might
     * be actively competing to synchronize on this object; for example,
     * the awakened threads enjoy no reliable privilege or disadvantage in
     * being the next thread to lock this object.
     * <p>
     * This method should only be called by a thread that is the owner
     * of this object's monitor. See the {@code notify} method for a
     * description of the ways in which a thread can become the owner of
     * a monitor.
     *
     * @throws  IllegalMonitorStateException  if the current thread is not
     *               the owner of this object's monitor.
     */
    @HotSpotIntrinsicCandidate
    public final native void notifyAll();
}
```

### `java.lang.Integer`

```java
package java.lang;

/**
 * The {@code Integer} class wraps a value of the primitive type
 * {@code int} in an object. An object of type {@code Integer}
 * contains a single field whose type is {@code int}.
 */
public final class Integer extends Number implements Comparable<Integer> {
    /**
     * Constructs a newly allocated {@code Integer} object that
     * represents the specified {@code int} value.
     *
     * @param   value   the value to be represented by the
     *                  {@code Integer} object.
     *
     * @deprecated
     * It is rarely appropriate to use this constructor. The static factory
     * {@link #valueOf(int)} is generally a better choice, as it is
     * likely to yield significantly better space and time performance.
     */
    @Deprecated(since="9")
    public Integer(int value);

    /**
     * Constructs a newly allocated {@code Integer} object that
     * represents the {@code int} value indicated by the
     * {@code String} parameter. The string is converted to an
     * {@code int} value in exactly the manner used by the
     * {@code parseInt} method for radix 10.
     *
     * @param   s   the {@code String} to be converted to an {@code Integer}.
     * @throws      NumberFormatException if the {@code String} does not
     *              contain a parsable integer.
     *
     * @deprecated
     * It is rarely appropriate to use this constructor.
     * Use {@link #parseInt(String)} to convert a string to a
     * {@code int} primitive, or use {@link #valueOf(String)}
     * to convert a string to an {@code Integer} object.
     */
    @Deprecated(since="9")
    public Integer(String s) throws NumberFormatException;

    /**
     * Returns an {@code Integer} object holding the
     * value of the specified {@code String}. The argument is
     * interpreted as representing a signed decimal integer, exactly
     * as if the argument were given to the {@link
     * #parseInt(java.lang.String)} method. The result is an
     * {@code Integer} object that represents the integer value
     * specified by the string.
     *
     * @param      s   the string to be parsed.
     * @return     an {@code Integer} object holding the value
     *             represented by the string argument.
     * @exception  NumberFormatException  if the string cannot be parsed
     *             as an integer.
     */
    public static Integer valueOf(String s) throws NumberFormatException;

    /**
     * Parses the string argument as a signed decimal integer. The
     * characters in the string must all be decimal digits, except
     * that the first character may be an ASCII minus sign {@code '-'}
     * to indicate a negative value or an ASCII plus sign {@code '+'} to
     * indicate a positive value. The resulting integer value is
     * returned, exactly as if the argument and the radix 10 were
     * given as arguments to the {@link #parseInt(java.lang.String,
     * int)} method.
     *
     * @param s    a {@code String} containing the {@code int}
     *             representation to be parsed
     * @return     the integer value represented by the argument in decimal.
     * @exception  NumberFormatException  if the string does not contain a
     *               parsable integer.
     */
    public static int parseInt(String s) throws NumberFormatException;

    /**
     * A constant holding the minimum value an {@code int} can
     * have, -2<sup>31</sup>.
     */
    @Native public static final int   MIN_VALUE = 0x80000000;

    /**
     * A constant holding the maximum value an {@code int} can
     * have, 2<sup>31</sup>-1.
     */
    @Native public static final int   MAX_VALUE = 0x7fffffff;
}
```

### `java.lang.Number`

```java
package java.lang;

/**
 * The abstract class {@code Number} is the superclass of platform
 * classes representing numeric values that are convertible to the
 * primitive types {@code byte}, {@code double}, {@code float}, {@code
 * int}, {@code long}, and {@code short}.
 */
public abstract class Number implements java.io.Serializable {
    /**
     * Returns the value of the specified number as an {@code int}.
     *
     * @return  the numeric value represented by this object after conversion
     *          to type {@code int}.
     */
    public abstract int intValue();

    /**
     * Returns the value of the specified number as a {@code long}.
     *
     * @return  the numeric value represented by this object after conversion
     *          to type {@code long}.
     */
    public abstract long longValue();

    /**
     * Returns the value of the specified number as a {@code float}.
     *
     * @return  the numeric value represented by this object after conversion
     *          to type {@code float}.
     */
    public abstract float floatValue();

    /**
     * Returns the value of the specified number as a {@code double}.
     *
     * @return  the numeric value represented by this object after conversion
     *          to type {@code double}.
     */
    public abstract double doubleValue();

    /**
     * Returns the value of the specified number as a {@code byte}.
     *
     * <p>This implementation returns the result of {@link #intValue} cast
     * to a {@code byte}.
     *
     * @return  the numeric value represented by this object after conversion
     *          to type {@code byte}.
     */
    public byte byteValue();

    /**
     * Returns the value of the specified number as a {@code short}.
     *
     * <p>This implementation returns the result of {@link #intValue} cast
     * to a {@code short}.
     *
     * @return  the numeric value represented by this object after conversion
     *          to type {@code short}.
     */
    public short shortValue();
}
```

### `java.lang.Exception`

```java
package java.lang;

/**
 * The class {@code Exception} and its subclasses are a form of
 * {@code Throwable} that indicates conditions that a reasonable
 * application might want to catch.
 */
public class Exception extends Throwable {
    /**
     * Constructs a new exception with {@code null} as its detail message.
     * The cause is not initialized, and may subsequently be initialized by a
     * call to {@link #initCause}.
     */
    public Exception();

    /**
     * Constructs a new exception with the specified detail message.  The
     * cause is not initialized, and may subsequently be initialized by
     * a call to {@link #initCause}.
     *
     * @param   message   the detail message. The detail message is saved for
     *          later retrieval by the {@link #getMessage()} method.
     */
    public Exception(String message);

    /**
     * Returns the detail message string of this throwable.
     *
     * @return  the detail message string of this {@code Throwable} instance
     *          (which may be {@code null}).
     */
    public String getMessage();

    /**
     * Returns a short description of this throwable.
     * The result is the concatenation of:
     * <ul>
     * <li> the {@linkplain Class#getName() name} of the class of this object
     * <li> ": " (a colon and a space)
     * <li> the result of invoking this object's {@link #getLocalizedMessage}
     *      method
     * </ul>
     *
     * @return a string representation of this throwable.
     */
    public String toString();

    /**
         * Prints this throwable and its backtrace to the
         * standard error stream. This method prints a stack trace for this
         * {@code Throwable} object on the error output stream that is
         * the value of the field {@code System.err}. The first line of
         * output contains the result of the {@link #toString()} method for
         * this object.
         */
        public void printStackTrace();
}
```

### `java.io.PrintWriter`

```java
package java.io;

/**
 * Prints formatted representations of objects to a text-output stream.  This
 * class implements all of the {@code print} methods found in {@link
 * PrintStream}.
 *
 * <p> Methods in this class never throw I/O exceptions, although some of its
 * constructors may.  The client may inquire as to whether any errors have
 * occurred by invoking {@link #checkError checkError()}.
 */
public class PrintWriter extends Writer {
    /**
     * Creates a new PrintWriter, without automatic line flushing, with the
     * specified file name.
     *
     * @param  fileName
     *         The name of the file to use as the destination of this writer.
     *         If the file exists then it will be truncated to zero size;
     *         otherwise, a new file will be created.  The output will be
     *         written to the file and is buffered.
     *
     * @throws  FileNotFoundException
     *          If the given string does not denote an existing, writable
     *          regular file and a new regular file of that name cannot be
     *          created, or if some other error occurs while opening or
     *          creating the file
     *
     * @throws  SecurityException
     *          If a security manager is present and {@link
     *          SecurityManager#checkWrite checkWrite(fileName)} denies write
     *          access to the file
     */
    public PrintWriter(String fileName) throws FileNotFoundException;

    // overloaded print(...)
    // overloaded println(...)
    // overloaded printf(...)
}
```

### `java.io.Scanner`

```java
package java.io;

/**
 * A simple text scanner which can parse primitive types and strings using
 * regular expressions.
 *
 * <p>A scanning operation may block waiting for input.
 *
 * <p>When a scanner throws an {@link InputMismatchException}, the scanner
 * will not pass the token that caused the exception, so that it may be
 * retrieved or skipped via some other method.
 *
 * <p>Unless otherwise mentioned, passing a {@code null} parameter into
 * any method of a {@code Scanner} will cause a
 * {@code NullPointerException} to be thrown.
 */
public final class Scanner implements Iterator<String>, Closeable {
    /**
     * Constructs a new {@code Scanner} that produces values scanned
     * from the specified file. Bytes from the file are converted into
     * characters using the underlying platform's
     * {@linkplain java.nio.charset.Charset#defaultCharset() default charset}.
     *
     * @param  source A file to be scanned
     * @throws FileNotFoundException if source is not found
     */
    public Scanner(File source) throws FileNotFoundException;

    /**
     * Constructs a new {@code Scanner} that produces values scanned
     * from the specified string.
     *
     * @param  source A string to scan
     */
    public Scanner(String source);

    /**
     * Closes this scanner.
     *
     * <p> If this scanner has not yet been closed then if its underlying
     * {@linkplain java.lang.Readable readable} also implements the {@link
     * java.io.Closeable} interface then the readable's {@code close} method
     * will be invoked.  If this scanner is already closed then invoking this
     * method will have no effect.
     *
     * <p>Attempting to perform search operations after a scanner has
     * been closed will result in an {@link IllegalStateException}.
     *
     */
    public void close();

    /**
     * Returns true if this scanner has another token in its input.
     * This method may block while waiting for input to scan.
     * The scanner does not advance past any input.
     *
     * @return true if and only if this scanner has another token
     * @throws IllegalStateException if this scanner is closed
     */
    public boolean hasNext();

    /**
     * Finds and returns the next complete token from this scanner.
     * A complete token is preceded and followed by input that matches
     * the delimiter pattern. This method may block while waiting for input
     * to scan, even if a previous invocation of {@link #hasNext} returned
     * {@code true}.
     *
     * @return the next token
     * @throws NoSuchElementException if no more tokens are available
     * @throws IllegalStateException if this scanner is closed
     */
    public String next();

    /**
     * Scans the next token of the input as a {@code byte}.
     *
     * @return the {@code byte} scanned from the input
     * @throws InputMismatchException
     *         if the next token does not match the <i>Integer</i>
     *         regular expression, or is out of range
     * @throws NoSuchElementException if input is exhausted
     * @throws IllegalStateException if this scanner is closed
     */
    public byte nextByte();

    /**
     * Scans the next token of the input as a {@code short}.
     *
     * @return the {@code short} scanned from the input
     * @throws InputMismatchException
     *         if the next token does not match the <i>Integer</i>
     *         regular expression, or is out of range
     * @throws NoSuchElementException if input is exhausted
     * @throws IllegalStateException if this scanner is closed
     */
    public short nextShort();

    /**
     * Scans the next token of the input as an {@code int}.
     *
     * @return the {@code int} scanned from the input
     * @throws InputMismatchException
     *         if the next token does not match the <i>Integer</i>
     *         regular expression, or is out of range
     * @throws NoSuchElementException if input is exhausted
     * @throws IllegalStateException if this scanner is closed
     */
    public int nextInt();

    /**
     * Scans the next token of the input as a {@code long}.
     *
     * @return the {@code long} scanned from the input
     * @throws InputMismatchException
     *         if the next token does not match the <i>Integer</i>
     *         regular expression, or is out of range
     * @throws NoSuchElementException if input is exhausted
     * @throws IllegalStateException if this scanner is closed
     */
    public long nextLong();

    /**
     * Scans the next token of the input as a {@code float}.
     * This method will throw {@code InputMismatchException}
     * if the next token cannot be translated into a valid float value as
     * described below. If the translation is successful, the scanner advances
     * past the input that matched.
     *
     * @return the {@code float} scanned from the input
     * @throws InputMismatchException
     *         if the next token does not match the <i>Float</i>
     *         regular expression, or is out of range
     * @throws NoSuchElementException if input is exhausted
     * @throws IllegalStateException if this scanner is closed
     */
    public float nextFloat();

    /**
     * Scans the next token of the input as a {@code double}.
     * This method will throw {@code InputMismatchException}
     * if the next token cannot be translated into a valid double value.
     * If the translation is successful, the scanner advances past the input
     * that matched.
     *
     * @return the {@code double} scanned from the input
     * @throws InputMismatchException
     *         if the next token does not match the <i>Float</i>
     *         regular expression, or is out of range
     * @throws NoSuchElementException if the input is exhausted
     * @throws IllegalStateException if this scanner is closed
     */
    public double nextDouble();

    /**
     * Sets this scanner's delimiting pattern to a pattern constructed from
     * the specified {@code String}.
     *
     * <p> Invoking the {@link #reset} method will set the scanner's delimiter
     * to the <a href= "#default-delimiter">default</a>.
     *
     * @param pattern A string specifying a delimiting pattern
     * @return this scanner
     */
    public Scanner useDelimiter(String pattern);
}
```

### `java.util.Comparable<T>`

```java
package java.util;

/**
 * This interface imposes a total ordering on the objects of each class that
 * implements it.
 *
 * @param <T> the type of objects that this object may be compared to
 */
public interface Comparable<T> {
    /**
     * Compares this object with the specified object for order.  Returns a
     * negative integer, zero, or a positive integer as this object is less
     * than, equal to, or greater than the specified object.
     *
     * @param   o the object to be compared.
     * @return  a negative integer, zero, or a positive integer as this object
     *          is less than, equal to, or greater than the specified object.
     *
     * @throws NullPointerException if the specified object is null
     * @throws ClassCastException if the specified object's type prevents it
     *         from being compared to this object.
     */
    public int compareTo(T o);
}
```

### `java.util.Cloneable`

```java
package java.util;

/**
 * A class implements the <code>Cloneable</code> interface to
 * indicate to the {@link java.lang.Object#clone()} method that it
 * is legal for that method to make a
 * field-for-field copy of instances of that class.
 * <p>
 * Invoking Object's clone method on an instance that does not implement the
 * <code>Cloneable</code> interface results in the exception
 * <code>CloneNotSupportedException</code> being thrown.
 */
public interface Cloneable {}
```

### `javafx.beans.property.Property<T>`

```java
package javafx.beans.property;

package javafx.beans.property;

import javafx.beans.value.ObservableValue;
import javafx.beans.value.WritableValue;

/**
 * Generic interface that defines the methods common to all (writable)
 * properties independent of their type.
 *
 * @param <T>
 *            the type of the wrapped value
 */
public interface Property<T> extends ReadOnlyProperty<T>, WritableValue<T> {
    /**
     * Create a unidirection binding for this {@code Property}.
     *
     * @param observable
     *            The observable this {@code Property} should be bound to.
     * @throws NullPointerException
     *             if {@code observable} is {@code null}
     */
    void bind(ObservableValue<? extends T> observable);

    /**
     * Remove the unidirectional binding for this {@code Property}.
     *
     * If the {@code Property} is not bound, calling this method has no effect.
     */
    void unbind();

    /**
     * Can be used to check, if a {@code Property} is bound.
     *
     * @return {@code true} if the {@code Property} is bound, {@code false}
     *         otherwise
     */
    boolean isBound();

    /**
     * Create a bidirectional binding between this {@code Property} and another
     * one.
     * Bidirectional bindings exists independently of unidirectional bindings. So it is possible to
     * add unidirectional binding to a property with bidirectional binding and vice-versa. However, this practice is
     * discouraged.
     * <p>
     * It is possible to have multiple bidirectional bindings of one Property.
     *
     * @param other
     *            the other {@code Property}
     * @throws NullPointerException
     *             if {@code other} is {@code null}
     * @throws IllegalArgumentException
     *             if {@code other} is {@code this}
     */
    void bindBidirectional(Property<T> other);

    /**
     * Remove a bidirectional binding between this {@code Property} and another
     * one.
     *
     * If no bidirectional binding between the properties exists, calling this
     * method has no effect.
     *
     * It is possible to unbind by a call on the second property. This code will work:
     *
     * <blockquote><pre>
     *     property1.bindBirectional(property2);
     *     property2.unbindBidirectional(property1);
     * </pre></blockquote>
     *
     * @param other
     *            the other {@code Property}
     * @throws NullPointerException
     *             if {@code other} is {@code null}
     * @throws IllegalArgumentException
     *             if {@code other} is {@code this}
     */
    void unbindBidirectional(Property<T> other);
}
```

### `javafx.scene.input.MouseEvent`

```java
package javafx.scene.input;

/**
 * When mouse event occurs, the top-most node under cursor is picked and
 * the event is delivered to it through capturing and bubbling phases
 * described at {@link javafx.event.EventDispatcher EventDispatcher}.
 * <p>
 * The mouse (pointer's) location is available relative to several
 * coordinate systems: x,y - relative to the origin of the
 * MouseEvent's node, sceneX,sceneY - relative to to the
 * origin of the {@code Scene} that contains the node,
 * screenX,screenY - relative to origin of the screen that
 * contains the mouse pointer.
 */
public class MouseEvent extends InputEvent {
    /**
     * Which, if any, of the mouse buttons is responsible for this event.
     *
     * @return mouse button whose state change caused this event
     */
    public final MouseButton getButton();

    /**
     * Returns number of mouse clicks associated with this event. The
     * value is increased with MOUSE_PRESSED event and stays like
     * that for all subsequent events till MOUSE_RELEASED, including the
     * afterwards generated MOUSE_CLICKED event. The value is increased
     * to numbers higher than one if all the events between two subsequent
     * presses happen on a small region and in a small time (according
     * to native operating system configuration).
     *
     * @return number of mouse clicks associated with this event
     */
    public final int getClickCount();

    /**
     * Horizontal position of the event relative to the
     * origin of the MouseEvent's source.
     *
     * @return horizontal position of the event relative to the
     * origin of the MouseEvent's source.
     */
    public final double getX();

    /**
     * Vertical position of the event relative to the
     * origin of the MouseEvent's source.
     *
     * @return vertical position of the event relative to the
     * origin of the MouseEvent's source.
     */
    public final double getY();

    /**
     * Returns horizontal position of the event relative to the
     * origin of the {@code Scene} that contains the MouseEvent's source.
     * If the node is not in a {@code Scene}, then the value is relative to
     * the boundsInParent of the root-most parent of the MouseEvent's node.
     * Note that in 3D scene, this represents the flat coordinates after
     * applying the projection transformations.
     *
     * @return horizontal position of the event relative to the
     * origin of the {@code Scene} that contains the MouseEvent's source
     */
    public final double getSceneX();

    /**
     * Returns vertical position of the event relative to the
     * origin of the {@code Scene} that contains the MouseEvent's source.
     * If the node is not in a {@code Scene}, then the value is relative to
     * the boundsInParent of the root-most parent of the MouseEvent's node.
     * Note that in 3D scene, this represents the flat coordinates after
     * applying the projection transformations.
     *
     * @return vertical position of the event relative to the
     * origin of the {@code Scene} that contains the MouseEvent's source
     */
    public final double getSceneY();

    /**
     * Returns absolute horizontal position of the event.
     * @return absolute horizontal position of the event
     */
    public final double getScreenX();

    /**
     * Returns absolute vertical position of the event.
     * @return absolute vertical position of the event
     */
    public final double getScreenY();

    /**
     * Whether or not the Alt modifier is down on this event.
     * @return true if the Alt modifier is down on this event
     */
    public final boolean isAltDown();

    /**
     * Whether or not the Control modifier is down on this event.
     * @return true if the Control modifier is down on this event
     */
    public final boolean isControlDown();

    /**
     * Whether or not the Meta modifier is down on this event.
     * @return true if the Meta modifier is down on this event
     */
    public final boolean isMetaDown();

    /**
     * Whether or not the Shift modifier is down on this event.
     * @return true if the Shift modifier is down on this event
     */
    public final boolean isShiftDown();
}
```

### `javafx.scene.input.KeyEvent`

```java
package javafx.scene.input;

/**
 * An event which indicates that a keystroke occurred in a component.
 * <p>
 * This low-level event is generated by a component object (such as a text
 * field) when a key is pressed, released, or typed.
 * The event is passed to every {@code KeyListener}
 * or {@code KeyAdapter} object which registered to receive such
 * events using the component's {@code addKeyListener} method.
 * ({@code KeyAdapter} objects implement the
 * {@code KeyListener} interface.)  Each such listener object
 * gets this {@code KeyEvent} when the event occurs.
 */
public final class KeyEvent extends InputEvent {
    /**
     * The Unicode character or sequence of characters associated with the key
     * typed event. Contains multiple elements if the key produced a single
     * Unicode character from outside of the Basic Multilingual Plane which
     * needs to be encoded by the corresponding surrogate pair in Java or if
     * the key produced multiple Unicode characters itself.
     *
     * @return The Unicode character(s) associated with the key typed event
     */
    public final String getCharacter();

    /**
     * The key code associated with the key in this key pressed or key released
     * event. For key typed events, {@code code} is always {@code KeyCode.UNDEFINED}.
     *
     * @return The key code associated with the key in this event,
     * {@code KeyCode.UNDEFINED} for key typed event
     */
    public final KeyCode getCode();

    /**
     * A String describing the key code, such as "HOME", "F1" or "A",
     * for key pressed and key released events.
     * For key typed events, {@code text} is always the empty string.
     *
     * @return A String describing the key code
     */
    public final String getText();

    /**
     * Returns whether or not the Alt modifier is down on this event.
     * @return whether or not the Alt modifier is down on this event.
     */
    public final boolean isAltDown();

    /**
     * Returns whether or not the Control modifier is down on this event.
     * @return whether or not the Control modifier is down on this event.
     */
    public final boolean isControlDown();

    /**
     * Returns whether or not the Meta modifier is down on this event.
     * @return whether or not the Meta modifier is down on this event.
     */
    public final boolean isMetaDown();

    /**
     * Returns whether or not the Shift modifier is down on this event.
     * @return whether or not the Shift modifier is down on this event.
     */
    public final boolean isShiftDown();
}
```

### `java.lang.Thread`

```java
package java.lang;

/**
 * A <i>thread</i> is a thread of execution in a program. The Java
 * Virtual Machine allows an application to have multiple threads of
 * execution running concurrently.
 * <p>
 * Every thread has a priority. Threads with higher priority are
 * executed in preference to threads with lower priority. Each thread
 * may or may not also be marked as a daemon. When code running in
 * some thread creates a new {@code Thread} object, the new
 * thread has its priority initially set equal to the priority of the
 * creating thread, and is a daemon thread if and only if the
 * creating thread is a daemon.
 * <p>
 * When a Java Virtual Machine starts up, there is usually a single
 * non-daemon thread (which typically calls the method named
 * {@code main} of some designated class). The Java Virtual
 * Machine continues to execute threads until either of the following
 * occurs:
 * <ul>
 * <li>The {@code exit} method of class {@code Runtime} has been
 *     called and the security manager has permitted the exit operation
 *     to take place.
 * <li>All threads that are not daemon threads have died, either by
 *     returning from the call to the {@code run} method or by
 *     throwing an exception that propagates beyond the {@code run}
 *     method.
 * </ul>
 * <p>
 * Unless otherwise noted, passing a {@code null} argument to a constructor
 * or method in this class will cause a {@link NullPointerException} to be
 * thrown.
 */
public class Thread implements Runnable {
    /**
     * The minimum priority that a thread can have.
     */
    public static final int MIN_PRIORITY = 1;

   /**
     * The default priority that is assigned to a thread.
     */
    public static final int NORM_PRIORITY = 5;

    /**
     * The maximum priority that a thread can have.
     */
    public static final int MAX_PRIORITY = 10;

    /**
     * Allocates a new {@code Thread} object. This constructor has the same
     * effect as {@linkplain #Thread(ThreadGroup,Runnable,String) Thread}
     * {@code (null, null, gname)}, where {@code gname} is a newly generated
     * name.
     */
    public Thread();

    /**
     * Allocates a new {@code Thread} object. This constructor has the same
     * effect as {@linkplain #Thread(ThreadGroup,Runnable,String) Thread}
     * {@code (null, target, gname)}, where {@code gname} is a newly generated
     * name.
     *
     * @param  target
     *         the object whose {@code run} method is invoked when this thread
     *         is started. If {@code null}, this classes {@code run} method does
     *         nothing.
     */
    public Thread(Runnable target);

    /**
     * Causes this thread to begin execution; the Java Virtual Machine
     * calls the {@code run} method of this thread.
     * <p>
     * The result is that two threads are running concurrently: the
     * current thread (which returns from the call to the
     * {@code start} method) and the other thread (which executes its
     * {@code run} method).
     * <p>
     * It is never legal to start a thread more than once.
     * In particular, a thread may not be restarted once it has completed
     * execution.
     *
     * @throws     IllegalThreadStateException  if the thread was already started.
     */
    public synchronized void start();

    /**
     * Tests if this thread is alive. A thread is alive if it has
     * been started and has not yet died.
     *
     * @return  {@code true} if this thread is alive;
     *          {@code false} otherwise.
     */
    public final native boolean isAlive();

    /**
     * Changes the priority of this thread.
     * <p>
     * First the {@code checkAccess} method of this thread is called
     * with no arguments. This may result in throwing a {@code SecurityException}.
     * <p>
     * Otherwise, the priority of this thread is set to the smaller of
     * the specified {@code newPriority} and the maximum permitted
     * priority of the thread's thread group.
     *
     * @param newPriority priority to set this thread to
     * @throws     IllegalArgumentException  If the priority is not in the
     *               range {@code MIN_PRIORITY} to
     *               {@code MAX_PRIORITY}.
     * @throws     SecurityException  if the current thread cannot modify
     *               this thread.
     */
    public final void setPriority(int newPriority);

    /**
     * Waits for this thread to die.
     *
     * <p> An invocation of this method behaves in exactly the same
     * way as the invocation
     *
     * <blockquote>
     * {@linkplain #join(long) join}{@code (0)}
     * </blockquote>
     *
     * @throws  InterruptedException
     *          if any thread has interrupted the current thread. The
     *          <i>interrupted status</i> of the current thread is
     *          cleared when this exception is thrown.
     */
    public final void join() throws InterruptedException;

    /**
     * Causes the currently executing thread to sleep (temporarily cease
     * execution) for the specified number of milliseconds, subject to
     * the precision and accuracy of system timers and schedulers. The thread
     * does not lose ownership of any monitors.
     *
     * @param  millis
     *         the length of time to sleep in milliseconds
     *
     * @throws  IllegalArgumentException
     *          if the value of {@code millis} is negative
     *
     * @throws  InterruptedException
     *          if any thread has interrupted the current thread. The
     *          <i>interrupted status</i> of the current thread is
     *          cleared when this exception is thrown.
     */
    public static native void sleep(long millis) throws InterruptedException;

    /**
     * A hint to the scheduler that the current thread is willing to yield
     * its current use of a processor. The scheduler is free to ignore this
     * hint.
     *
     * <p> Yield is a heuristic attempt to improve relative progression
     * between threads that would otherwise over-utilise a CPU. Its use
     * should be combined with detailed profiling and benchmarking to
     * ensure that it actually has the desired effect.
     */
    public static native void yield();

    /**
     * Interrupts this thread.
     *
     * <p> Unless the current thread is interrupting itself, which is
     * always permitted, the {@link #checkAccess() checkAccess} method
     * of this thread is invoked, which may cause a {@link
     * SecurityException} to be thrown.
     *
     * <p> If this thread is blocked in an invocation of the {@link
     * Object#wait() wait()}, {@link Object#wait(long) wait(long)}, or {@link
     * Object#wait(long, int) wait(long, int)} methods of the {@link Object}
     * class, or of the {@link #join()}, {@link #join(long)}, {@link
     * #join(long, int)}, {@link #sleep(long)}, or {@link #sleep(long, int)},
     * methods of this class, then its interrupt status will be cleared and it
     * will receive an {@link InterruptedException}.
     *
     * <p> If none of the previous conditions hold then this thread's interrupt
     * status will be set. </p>
     *
     * <p> Interrupting a thread that is not alive need not have any effect.
     *
     * @throws  SecurityException
     *          if the current thread cannot modify this thread
     */
    public void interrupt();
}
```

### `java.util.concurrent.Executor`

```java
package java.util.concurrent;

/**
 * An object that executes submitted {@link Runnable} tasks. This
 * interface provides a way of decoupling task submission from the
 * mechanics of how each task will be run, including details of thread
 * use, scheduling, etc.  An {@code Executor} is normally used
 * instead of explicitly creating threads.
 */
public interface Executor {

    /**
     * Executes the given command at some time in the future.  The command
     * may execute in a new thread, in a pooled thread, or in the calling
     * thread, at the discretion of the {@code Executor} implementation.
     *
     * @param command the runnable task
     * @throws RejectedExecutionException if this task cannot be
     * accepted for execution
     * @throws NullPointerException if command is null
     */
    void execute(Runnable command);
}
```

### `java.util.concurrent.ExecutorService`

```java
package java.util.concurrent;

/**
 * An {@link Executor} that provides methods to manage termination and
 * methods that can produce a {@link Future} for tracking progress of
 * one or more asynchronous tasks.
 */
public interface ExecutorService extends Executor {

    /**
     * Initiates an orderly shutdown in which previously submitted
     * tasks are executed, but no new tasks will be accepted.
     * Invocation has no additional effect if already shut down.
     *
     * <p>This method does not wait for previously submitted tasks to
     * complete execution.  Use {@link #awaitTermination awaitTermination}
     * to do that.
     *
     * @throws SecurityException if a security manager exists and
     *         shutting down this ExecutorService may manipulate
     *         threads that the caller is not permitted to modify
     *         because it does not hold {@link
     *         java.lang.RuntimePermission}{@code ("modifyThread")},
     *         or the security manager's {@code checkAccess} method
     *         denies access.
     */
    void shutdown();

    /**
     * Attempts to stop all actively executing tasks, halts the
     * processing of waiting tasks, and returns a list of the tasks
     * that were awaiting execution.
     *
     * @return list of tasks that never commenced execution
     * @throws SecurityException if a security manager exists and
     *         shutting down this ExecutorService may manipulate
     *         threads that the caller is not permitted to modify
     *         because it does not hold {@link
     *         java.lang.RuntimePermission}{@code ("modifyThread")},
     *         or the security manager's {@code checkAccess} method
     *         denies access.
     */
    List<Runnable> shutdownNow();

    /**
     * Returns {@code true} if this executor has been shut down.
     *
     * @return {@code true} if this executor has been shut down
     */
    boolean isShutdown();

    /**
     * Returns {@code true} if all tasks have completed following shut down.
     * Note that {@code isTerminated} is never {@code true} unless
     * either {@code shutdown} or {@code shutdownNow} was called first.
     *
     * @return {@code true} if all tasks have completed following shut down
     */
    boolean isTerminated();
}
```

### `java.util.concurrent.Executors`

```java
package java.util.concurrent;

/**
 * Factory and utility methods for {@link Executor}, {@link
 * ExecutorService}, {@link ScheduledExecutorService}, {@link
 * ThreadFactory}, and {@link Callable} classes defined in this
 * package.
 */
public class Executors {
    /**
     * Creates a thread pool that reuses a fixed number of threads
     * operating off a shared unbounded queue.  At any point, at most
     * {@code nThreads} threads will be active processing tasks.
     * If additional tasks are submitted when all threads are active,
     * they will wait in the queue until a thread is available.
     * The threads in the pool will exist until it is explicitly
     * {@link ExecutorService#shutdown shutdown}.
     *
     * @param nThreads the number of threads in the pool
     * @return the newly created thread pool
     * @throws IllegalArgumentException if {@code nThreads <= 0}
     */
    public static ExecutorService newFixedThreadPool(int nThreads);

    /**
     * Creates a thread pool that creates new threads as needed, but
     * will reuse previously constructed threads when they are
     * available. Calls to {@code execute} will reuse previously
     * constructed threads if available. If no existing thread is
     * available, a new thread will be created and added to the pool.
     *
     * @return the newly created thread pool
     */
    public static ExecutorService newCachedThreadPool();
}
```

### `java.util.concurrent.locks.Lock`

```java
package java.util.concurrent.locks;

/**
 * {@code Lock} implementations provide more extensive locking
 * operations than can be obtained using {@code synchronized} methods
 * and statements.
 *
 * <p>A lock is a tool for controlling access to a shared resource by
 * multiple threads. Commonly, a lock provides exclusive access to a
 * shared resource: only one thread at a time can acquire the lock and
 * all access to the shared resource requires that the lock be
 * acquired first. However, some locks may allow concurrent access to
 * a shared resource, such as the read lock of a {@link ReadWriteLock}.
 *
 * When locking and unlocking occur in different scopes, care must be
 * taken to ensure that all code that is executed while the lock is
 * held is protected by try-finally or try-catch to ensure that the
 * lock is released when necessary.
 *
 * <p>Except where noted, passing a {@code null} value for any
 * parameter will result in a {@link NullPointerException} being
 * thrown.
 */
public interface Lock {
    /**
     * Acquires the lock.
     *
     * <p>If the lock is not available then the current thread becomes
     * disabled for thread scheduling purposes and lies dormant until the
     * lock has been acquired.
     */
    void lock();

    /**
     * Releases the lock.
     */
    void unlock();

    /**
     * Returns a new {@link Condition} instance that is bound to this
     * {@code Lock} instance.
     *
     * <p>Before waiting on the condition the lock must be held by the
     * current thread.
     * A call to {@link Condition#await()} will atomically release the lock
     * before waiting and re-acquire the lock before the wait returns.
     *
     * @return A new {@link Condition} instance for this {@code Lock} instance
     * @throws UnsupportedOperationException if this {@code Lock}
     *         implementation does not support conditions
     */
    Condition newCondition();
}
```

### `java.util.concurrent.locks.ReentrantLock`

```java
package java.util.concurrent.locks;

/**
 * A reentrant mutual exclusion {@link Lock} with the same basic
 * behavior and semantics as the implicit monitor lock accessed using
 * {@code synchronized} methods and statements, but with extended
 * capabilities.
 *
 * <p>A {@code ReentrantLock} is <em>owned</em> by the thread last
 * successfully locking, but not yet unlocking it. A thread invoking
 * {@code lock} will return, successfully acquiring the lock, when
 * the lock is not owned by another thread.
 *
 * <p>It is recommended practice to <em>always</em> immediately
 * follow a call to {@code lock} with a {@code try} block, most
 * typically in a before/after construction such as:
 *
 * <pre> {@code
 * class X {
 *   private final ReentrantLock lock = new ReentrantLock();
 *   // ...
 *
 *   public void m() {
 *     lock.lock();  // block until condition holds
 *     try {
 *       // ... method body
 *     } finally {
 *       lock.unlock()
 *     }
 *   }
 * }}</pre>
 */
public class ReentrantLock implements Lock, java.io.Serializable {
    /**
     * Creates an instance of {@code ReentrantLock}.
     * This is equivalent to using {@code ReentrantLock(false)}.
     */
    public ReentrantLock();

    /**
     * Creates an instance of {@code ReentrantLock} with the
     * given fairness policy.
     *
     * @param fair {@code true} if this lock should use a fair ordering policy
     */
    public ReentrantLock(boolean fair);
}
```

### `java.util.concurrent.locks.Condition`

```java
package java.util.concurrent.locks;

/**
 * {@code Condition} factors out the {@code Object} monitor
 * methods ({@link Object#wait() wait}, {@link Object#notify notify}
 * and {@link Object#notifyAll notifyAll}) into distinct objects to
 * give the effect of having multiple wait-sets per object, by
 * combining them with the use of arbitrary {@link Lock} implementations.
 * Where a {@code Lock} replaces the use of {@code synchronized} methods
 * and statements, a {@code Condition} replaces the use of the Object
 * monitor methods.
 *
 * <p>Conditions (also known as <em>condition queues</em> or
 * <em>condition variables</em>) provide a means for one thread to
 * suspend execution (to &quot;wait&quot;) until notified by another
 * thread that some state condition may now be true.  Because access
 * to this shared state information occurs in different threads, it
 * must be protected, so a lock of some form is associated with the
 * condition. The key property that waiting for a condition provides
 * is that it <em>atomically</em> releases the associated lock and
 * suspends the current thread, just like {@code Object.wait}.
 *
 * <p>A {@code Condition} instance is intrinsically bound to a lock.
 * To obtain a {@code Condition} instance for a particular {@link Lock}
 * instance use its {@link Lock#newCondition newCondition()} method.
 *
 * <p>Except where noted, passing a {@code null} value for any parameter
 * will result in a {@link NullPointerException} being thrown.
 */
public interface Condition {
    /**
     * Causes the current thread to wait until it is signalled or
     * {@linkplain Thread#interrupt interrupted}.
     *
     * <p>The lock associated with this {@code Condition} is atomically
     * released and the current thread becomes disabled for thread scheduling
     * purposes and lies dormant until <em>one</em> of four things happens:
     * <ul>
     * <li>Some other thread invokes the {@link #signal} method for this
     * {@code Condition} and the current thread happens to be chosen as the
     * thread to be awakened; or
     * <li>Some other thread invokes the {@link #signalAll} method for this
     * {@code Condition}; or
     * <li>Some other thread {@linkplain Thread#interrupt interrupts} the
     * current thread, and interruption of thread suspension is supported; or
     * <li>A &quot;<em>spurious wakeup</em>&quot; occurs.
     * </ul>
     *
     * <p>In all cases, before this method can return the current thread must
     * re-acquire the lock associated with this condition. When the
     * thread returns it is <em>guaranteed</em> to hold this lock.
     *
     * <p>If the current thread:
     * <ul>
     * <li>has its interrupted status set on entry to this method; or
     * <li>is {@linkplain Thread#interrupt interrupted} while waiting
     * and interruption of thread suspension is supported,
     * </ul>
     * then {@link InterruptedException} is thrown and the current thread's
     * interrupted status is cleared. It is not specified, in the first
     * case, whether or not the test for interruption occurs before the lock
     * is released.
     *
     * @throws InterruptedException if the current thread is interrupted
     *         (and interruption of thread suspension is supported)
     */
    void await() throws InterruptedException;

    /**
     * Wakes up one waiting thread.
     *
     * <p>If any threads are waiting on this condition then one
     * is selected for waking up. That thread must then re-acquire the
     * lock before returning from {@code await}.
     */
    void signal();

    /**
     * Wakes up all waiting threads.
     *
     * <p>If any threads are waiting on this condition then they are
     * all woken up. Each thread must re-acquire the lock before it can
     * return from {@code await}.
     */
    void signalAll();
}
```

### `java.lang.FunctionalInterface`

```java
package java.lang;

/**
 * An informative annotation type used to indicate that an interface
 * type declaration is intended to be a <i>functional interface</i> as
 * defined by the Java Language Specification.
 *
 * Conceptually, a functional interface has exactly one abstract
 * method.  Since {@linkplain java.lang.reflect.Method#isDefault()
 * default methods} have an implementation, they are not abstract.  If
 * an interface declares an abstract method overriding one of the
 * public methods of {@code java.lang.Object}, that also does
 * <em>not</em> count toward the interface's abstract method count
 * since any implementation of the interface will have an
 * implementation from {@code java.lang.Object} or elsewhere.
 */
@Documented
@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.TYPE)
public @interface FunctionalInterface {}
```

### `java.util.function.Predicate`

```java
package java.util.function;

/**
 * Represents a predicate (boolean-valued function) of one argument.
 *
 * @param <T> the type of the input to the predicate
 */
@FunctionalInterface
public interface Predicate<T> {
    /**
     * Evaluates this predicate on the given argument.
     *
     * @param t the input argument
     * @return {@code true} if the input argument matches the predicate,
     * otherwise {@code false}
     */
    boolean test(T t);

    /**
     * Returns a composed predicate that represents a short-circuiting logical
     * AND of this predicate and another.  When evaluating the composed
     * predicate, if this predicate is {@code false}, then the {@code other}
     * predicate is not evaluated.
     *
     * @param other a predicate that will be logically-ANDed with this
     *              predicate
     * @return a composed predicate that represents the short-circuiting logical
     * AND of this predicate and the {@code other} predicate
     * @throws NullPointerException if other is null
     */
    default Predicate<T> and(Predicate<? super T> other);

    /**
     * Returns a predicate that represents the logical negation of this
     * predicate.
     *
     * @return a predicate that represents the logical negation of this
     * predicate
     */
    default Predicate<T> negate();

    /**
     * Returns a composed predicate that represents a short-circuiting logical
     * OR of this predicate and another.  When evaluating the composed
     * predicate, if this predicate is {@code true}, then the {@code other}
     * predicate is not evaluated.
     *
     * @param other a predicate that will be logically-ORed with this
     *              predicate
     * @return a composed predicate that represents the short-circuiting logical
     * OR of this predicate and the {@code other} predicate
     * @throws NullPointerException if other is null
     */
    default Predicate<T> or(Predicate<? super T> other);

    /**
     * Returns a predicate that tests if two arguments are equal according
     * to {@link Objects#equals(Object, Object)}.
     *
     * @param <T> the type of arguments to the predicate
     * @param targetRef the object reference with which to compare for equality,
     *               which may be {@code null}
     * @return a predicate that tests if two arguments are equal according
     * to {@link Objects#equals(Object, Object)}
     */
    static <T> Predicate<T> isEqual(Object targetRef);
}
```

### `java.util.function.Function`

```java
package java.util.function;

/**
 * Represents a function that accepts one argument and produces a result.
 *
 * @param <T> the type of the input to the function
 * @param <R> the type of the result of the function
 */
@FunctionalInterface
public interface Function<T, R> {
    /**
     * Applies this function to the given argument.
     *
     * @param t the function argument
     * @return the function result
     */
    R apply(T t);

    /**
     * Returns a composed function that first applies the {@code before}
     * function to its input, and then applies this function to the result.
     * If evaluation of either function throws an exception, it is relayed to
     * the caller of the composed function.
     *
     * @param <V> the type of input to the {@code before} function, and to the
     *           composed function
     * @param before the function to apply before this function is applied
     * @return a composed function that first applies the {@code before}
     * function and then applies this function
     * @throws NullPointerException if before is null
     */
    default <V> Function<V, R> compose(Function<? super V, ? extends T> before);

    /**
     * Returns a function that always returns its input argument.
     *
     * @param <T> the type of the input and output objects to the function
     * @return a function that always returns its input argument
     */
    static <T> Function<T, T> identity();
}
```

### `java.util.function.Consumer`

```java
package java.util.function;

/**
 * Represents an operation that accepts a single input argument and returns no
 * result. Unlike most other functional interfaces, {@code Consumer} is expected
 * to operate via side-effects.
 *
 * @param <T> the type of the input to the operation
 */
@FunctionalInterface
public interface Consumer<T> {
    /**
     * Performs this operation on the given argument.
     *
     * @param t the input argument
     */
    void accept(T t);
}
```

### `java.util.function.Supplier`

```java
package java.util.function;

/**
 * Represents a supplier of results.
 *
 * <p>There is no requirement that a new or distinct result be returned each
 * time the supplier is invoked.
 *
 * @param <T> the type of results supplied by this supplier
 */
@FunctionalInterface
public interface Supplier<T> {
    /**
     * Gets a result.
     *
     * @return a result
     */
    T get();
}
```

### `java.util.stream.Stream`

```java
package java.util.stream;

/**
 * A sequence of elements supporting sequential and parallel aggregate
 * operations.
 *
 * <p>Streams are lazy; computation on the source data is only performed when the
 * terminal operation is initiated, and source elements are consumed only
 * as needed.
 *
 * <p>To preserve correct behavior, these <em>behavioral parameters</em>:
 * <ul>
 * <li>must be <a href="package-summary.html#NonInterference">non-interfering</a>
 * (they do not modify the stream source); and</li>
 * <li>in most cases must be <a href="package-summary.html#Statelessness">stateless</a>
 * (their result should not depend on any state that might change during execution
 * of the stream pipeline).</li>
 * </ul>
 *
 * <p>Such parameters are always instances of a
 * <a href="../function/package-summary.html">functional interface</a> such
 * as {@link java.util.function.Function}, and are often lambda expressions or
 * method references.  Unless otherwise specified these parameters must be
 * <em>non-null</em>.
 *
 * <p>A stream should be operated on (invoking an intermediate or terminal stream
 * operation) only once. A stream implementation may throw {@link IllegalStateException}
 * if it detects that the stream is being reused.
 *
 * <p>Stream pipelines may execute either sequentially or in
 * <a href="package-summary.html#Parallelism">parallel</a>.
 *
 * @param <T> the type of the stream elements
 */
public interface Stream<T> extends BaseStream<T, Stream<T>> {
    /**
     * Returns a stream consisting of the elements of this stream that match
     * the given predicate.
     *
     * <p>This is an <a href="package-summary.html#StreamOps">intermediate
     * operation</a>.
     *
     * @param predicate a <a href="package-summary.html#NonInterference">non-interfering</a>,
     *                  <a href="package-summary.html#Statelessness">stateless</a>
     *                  predicate to apply to each element to determine if it
     *                  should be included
     * @return the new stream
     */
    Stream<T> filter(Predicate<? super T> predicate);

    /**
     * Returns a stream consisting of the results of applying the given
     * function to the elements of this stream.
     *
     * <p>This is an <a href="package-summary.html#StreamOps">intermediate
     * operation</a>.
     *
     * @param <R> The element type of the new stream
     * @param mapper a <a href="package-summary.html#NonInterference">non-interfering</a>,
     *               <a href="package-summary.html#Statelessness">stateless</a>
     *               function to apply to each element
     * @return the new stream
     */
    <R> Stream<R> map(Function<? super T, ? extends R> mapper);

    /**
     * Performs a <a href="package-summary.html#Reduction">reduction</a> on the
     * elements of this stream, using the provided identity value and an
     * <a href="package-summary.html#Associativity">associative</a>
     * accumulation function, and returns the reduced value.  This is equivalent
     * to:
     * <pre>{@code
     *     T result = identity;
     *     for (T element : this stream)
     *         result = accumulator.apply(result, element)
     *     return result;
     * }</pre>
     *
     * but is not constrained to execute sequentially.
     *
     * <p>This is a <a href="package-summary.html#StreamOps">terminal
     * operation</a>.
     *
     * @param identity the identity value for the accumulating function
     * @param accumulator an <a href="package-summary.html#Associativity">associative</a>,
     *                    <a href="package-summary.html#NonInterference">non-interfering</a>,
     *                    <a href="package-summary.html#Statelessness">stateless</a>
     *                    function for combining two values
     * @return the result of the reduction
     */
    T reduce(T identity, BinaryOperator<T> accumulator);

    /**
     * Returns whether any elements of this stream match the provided
     * predicate.  May not evaluate the predicate on all elements if not
     * necessary for determining the result.  If the stream is empty then
     * {@code false} is returned and the predicate is not evaluated.
     *
     * <p>This is a <a href="package-summary.html#StreamOps">short-circuiting
     * terminal operation</a>.
     *
     * @param predicate a <a href="package-summary.html#NonInterference">non-interfering</a>,
     *                  <a href="package-summary.html#Statelessness">stateless</a>
     *                  predicate to apply to elements of this stream
     * @return {@code true} if any elements of the stream match the provided
     * predicate, otherwise {@code false}
     */
    boolean anyMatch(Predicate<? super T> predicate);

    /**
     * Returns whether all elements of this stream match the provided predicate.
     * May not evaluate the predicate on all elements if not necessary for
     * determining the result.  If the stream is empty then {@code true} is
     * returned and the predicate is not evaluated.
     *
     * <p>This is a <a href="package-summary.html#StreamOps">short-circuiting
     * terminal operation</a>.
     *
     * @param predicate a <a href="package-summary.html#NonInterference">non-interfering</a>,
     *                  <a href="package-summary.html#Statelessness">stateless</a>
     *                  predicate to apply to elements of this stream
     * @return {@code true} if either all elements of the stream match the
     * provided predicate or the stream is empty, otherwise {@code false}
     */
    boolean allMatch(Predicate<? super T> predicate);

    /**
     * Returns the count of elements in this stream.  This is a special case of
     * a <a href="package-summary.html#Reduction">reduction</a> and is
     * equivalent to:
     * <pre>{@code
     *     return mapToLong(e -> 1L).sum();
     * }</pre>
     *
     * <p>This is a <a href="package-summary.html#StreamOps">terminal operation</a>.
     *
     * @return the count of elements in this stream
     */
    long count();

    /**
     * Returns a sequential ordered stream whose elements are the specified values.
     *
     * @param <T> the type of stream elements
     * @param values the elements of the new stream
     * @return the new stream
     */
    @SafeVarargs
    @SuppressWarnings("varargs")
    public static<T> Stream<T> of(T... values);

    /**
     * Performs a <a href="package-summary.html#MutableReduction">mutable
     * reduction</a> operation on the elements of this stream using a
     * {@code Collector}.  A {@code Collector}
     * encapsulates the functions used as arguments to
     * {@link #collect(Supplier, BiConsumer, BiConsumer)}, allowing for reuse of
     * collection strategies and composition of collect operations such as
     * multiple-level grouping or partitioning.
     *
     * <p>This is a <a href="package-summary.html#StreamOps">terminal
     * operation</a>.

     * @apiNote
     * The following will accumulate strings into an ArrayList:
     * <pre>{@code
     *     List<String> asList = stringStream.collect(Collectors.toList());
     * }</pre>
     *
     * @param <R> the type of the result
     * @param <A> the intermediate accumulation type of the {@code Collector}
     * @param collector the {@code Collector} describing the reduction
     * @return the result of the reduction
     */
    <R, A> R collect(Collector<? super T, A, R> collector);

    /**
     * Returns an array containing the elements of this stream.
     *
     * <p>This is a <a href="package-summary.html#StreamOps">terminal
     * operation</a>.
     *
     * @return an array, whose {@linkplain Class#getComponentType runtime component
     * type} is {@code Object}, containing the elements of this stream
     */
    Object[] toArray();
}
```

## Appendix B: JUnit 5.3.2 API Documentation

### `org.junit.jupiter.api.Asserions`

```java
package org.junit.jupiter.api;

/**
 * {@code Assertions} is a collection of utility methods that support asserting
 * conditions in tests.
 *
 * <p>Unless otherwise noted, a <em>failed</em> assertion will throw an
 * {@link org.opentest4j.AssertionFailedError} or a subclass thereof.
 */
class Assertions {
    /**
	 * <em>Asserts</em> that {@code expected} and {@code actual} are equal.
	 * <p>If both are {@code null}, they are considered equal.
	 */
	public static void assertEquals(Object expected, Object actual)
    // assertEquals(...) primitive overloads

    /**
	 * <em>Asserts</em> that the supplied {@code condition} is {@code true}.
	 */
	public static void assertTrue(boolean condition);

    /**
	 * <em>Asserts</em> that the supplied {@code condition} is not {@code true}.
	 */
	public static void assertFalse(boolean condition);

    /**
	 * <em>Asserts</em> that execution of the supplied {@code executable} throws
	 * an exception of the {@code expectedType} and returns the exception.
	 *
	 * <p>If no exception is thrown, or if an exception of a different type is
	 * thrown, this method will fail.
	 *
	 * <p>If you do not want to perform additional checks on the exception instance,
	 * simply ignore the return value.
	 */
	public static <T extends Throwable> T assertThrows(Class<T> expectedType, Executable executable);
}
```

### `org.junit.jupiter.api.Test`

```java
package org.junit.jupiter.api;

/**
 * {@code @Test} is used to signal that the annotated method is a
 * <em>test</em> method.
 *
 * <p>{@code @Test} methods must not be {@code private} or {@code static}
 * and must not return a value.
 */
@Target({ ElementType.ANNOTATION_TYPE, ElementType.METHOD })
@Retention(RetentionPolicy.RUNTIME)
@Documented
@API(status = STABLE, since = "5.0")
@Testable
public @interface Test {}
```

### `org.junit.jupiter.api.BeforeAll`

```java
package org.junit.jupiter.api;

/**
 * {@code @BeforeAll} is used to signal that the annotated method should be
 * executed <em>before</em> <strong>all</strong> tests in the current test class.
 *
 * <p>In contrast to {@link BeforeEach @BeforeEach} methods, {@code @BeforeAll}
 * methods are only executed once for a given test class.
 *
 * <h3>Method Signatures</h3>
 *
 * {@code @BeforeAll} methods must have a {@code void} return type,
 * must not be {@code private}, and must be {@code static} by default.
 * Consequently, {@code @BeforeAll} methods are not
 * supported in {@link Nested @Nested} test classes or as <em>interface default
 * methods</em> unless the test class is annotated with
 * {@link TestInstance @TestInstance(Lifecycle.PER_CLASS)}.
 */
@Target({ ElementType.ANNOTATION_TYPE, ElementType.METHOD })
@Retention(RetentionPolicy.RUNTIME)
@Documented
public @interface BeforeAll {}
```

### `org.junit.jupiter.api.BeforeEach`

```java
package org.junit.jupiter.api;

/**
 * {@code @BeforeEach} is used to signal that the annotated method should be
 * executed <em>before</em> <strong>each</strong> {@code @Test},
 * {@code @RepeatedTest}, {@code @ParameterizedTest}, {@code @TestFactory},
 * and {@code @TestTemplate} method in the current test class.
 *
 * <h3>Method Signatures</h3>
 *
 * {@code @BeforeEach} methods must have a {@code void} return type,
 * must not be {@code private}, and must not be {@code static}.
 */
@Target({ ElementType.ANNOTATION_TYPE, ElementType.METHOD })
@Retention(RetentionPolicy.RUNTIME)
@Documented
public @interface BeforeEach {}
```

### `org.junit.jupiter.api.AfterAll`

```java
package org.junit.jupiter.api;

/**
 * {@code @AfterAll} is used to signal that the annotated method should be
 * executed <em>after</em> <strong>all</strong> tests in the current test class.
 *
 * <p>In contrast to {@link AfterEach @AfterEach} methods, {@code @AfterAll}
 * methods are only executed once for a given test class.
 *
 * <h3>Method Signatures</h3>
 *
 * {@code @AfterAll} methods must have a {@code void} return type,
 * must not be {@code private}, and must be {@code static} by default.
 * Consequently, {@code @AfterAll} methods are not
 * supported in {@link Nested @Nested} test classes or as <em>interface default
 * methods</em> unless the test class is annotated with
 * {@link TestInstance @TestInstance(Lifecycle.PER_CLASS)}.
 */
@Target({ ElementType.ANNOTATION_TYPE, ElementType.METHOD })
@Retention(RetentionPolicy.RUNTIME)
@Documented
public @interface AfterAll {}
```

### `org.junit.jupiter.api.AfterEach`

```java
package org.junit.jupiter.api;

/**
 * {@code @AfterEach} is used to signal that the annotated method should be
 * executed <em>after</em> <strong>each</strong> {@code @Test},
 * {@code @RepeatedTest}, {@code @ParameterizedTest}, {@code @TestFactory},
 * and {@code @TestTemplate} method in the current test class.
 *
 * <h3>Method Signatures</h3>
 *
 * {@code @AfterEach} methods must have a {@code void} return type,
 * must not be {@code private}, and must not be {@code static}.
 */
@Target({ ElementType.ANNOTATION_TYPE, ElementType.METHOD })
@Retention(RetentionPolicy.RUNTIME)
@Documented
public @interface AfterEach {}
```

### `org.junit.jupiter.api.DisplayName`

```java
package org.junit.jupiter.api;

/**
 * {@code @DisplayName} is used to declare a {@linkplain #value custom display
 * name} for the annotated test class or test method.
 *
 * <p>Display names are typically used for test reporting in IDEs and build
 * tools and may contain spaces, special characters, and even emoji.
 */
@Target({ ElementType.TYPE, ElementType.METHOD })
@Retention(RetentionPolicy.RUNTIME)
@Documented
public @interface DisplayName {
	/**
	 * Custom display name for the annotated class or method.
	 *
	 * @return a custom display name; never blank or consisting solely of
	 * whitespace
	 */
	String value();
}
```

### `org.junit.jupiter.api.Disabled`

```java
package org.junit.jupiter.api;

/**
 * {@code @Disabled} is used to signal that the annotated test class or
 * test method is currently <em>disabled</em> and should not be executed.
 *
 * <p>{@code @Disabled} may optionally be declared with a {@linkplain #value
 * reason} to document why the annotated test class or test method is disabled.
 *
 * <p>When applied at the class level, all test methods within that class
 * are automatically disabled as well.
 *
 * <p>When applied at the method level, the presence of this annotation does not
 * prevent the test class from being instantiated. Rather, it prevents the
 * execution of the test method and method-level lifecycle callbacks such as
 * {@code @BeforeEach} methods, {@code @AfterEach} methods, and corresponding
 * extension APIs.
 */
@Target({ ElementType.TYPE, ElementType.METHOD })
@Retention(RetentionPolicy.RUNTIME)
@Documented
public @interface Disabled {
	/**
	 * The reason this annotated test class or test method is disabled.
	 */
	String value() default "";
}
```
