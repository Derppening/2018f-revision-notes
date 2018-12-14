## Appendix: API Documentation (by appearence in Lecture Notes)

### `java.util.ArrayList<E>`

```java
package java.util;

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
     * More formally, returns {@code true} if and only if this list contains
     * at least one element {@code e} such that
     * {@code Objects.equals(o, e)}.
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
     * More formally, returns the lowest index {@code i} such that
     * {@code Objects.equals(o, get(i))},
     * or -1 if there is no such index.
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
     * More formally, returns the highest index {@code i} such that
     * {@code Objects.equals(o, get(i))},
     * or -1 if there is no such index.
     */
    public int lastIndexOf(Object o);

    /**
     * Removes the first occurrence of the specified element from this list,
     * if it is present.  If the list does not contain the element, it is
     * unchanged.  More formally, removes the element with the lowest index
     * {@code i} such that
     * {@code Objects.equals(o, get(i))}
     * (if such an element exists).  Returns {@code true} if this list
     * contained the specified element (or equivalently, if this list
     * changed as a result of the call).
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
     * unchanged.  More formally, removes the element with the lowest index
     * {@code i} such that
     * {@code Objects.equals(o, get(i))}
     * (if such an element exists).  Returns {@code true} if this list
     * contained the specified element (or equivalently, if this list
     * changed as a result of the call).
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
}
```

### `java.util.Arrays`

```java
package java.util;

public class Arrays {
    /**
     * Returns a fixed-size list backed by the specified array. Changes made to
     * the array will be visible in the returned list, and changes made to the
     * list will be visible in the array. The returned list is
     * {@link Serializable} and implements {@link RandomAccess}.
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

public final class String
    implements java.io.Serializable, Comparable<String>, CharSequence {
    /**
     * Initializes a newly created {@code String} object so that it represents
     * an empty character sequence.  Note that use of this constructor is
     * unnecessary since Strings are immutable.
     */
    public String();

    /**
     * Initializes a newly created {@code String} object so that it represents
     * the same sequence of characters as the argument; in other words, the
     * newly created string is a copy of the argument string. Unless an
     * explicit copy of {@code original} is needed, use of this constructor is
     * unnecessary since Strings are immutable.
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
     * The comparison is based on the Unicode value of each character in
     * the strings. The character sequence represented by this
     * {@code String} object is compared lexicographically to the
     * character sequence represented by the argument string. The result is
     * a negative integer if this {@code String} object
     * lexicographically precedes the argument string. The result is a
     * positive integer if this {@code String} object lexicographically
     * follows the argument string. The result is zero if the strings
     * are equal; {@code compareTo} returns {@code 0} exactly when
     * the {@link #equals(Object)} method would return {@code true}.
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
     * The length is equal to the number of <a href="Character.html#unicode">Unicode
     * code units</a> in the string.
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
     * <p>
     * If the length of the argument string is {@code 0}, then this
     * {@code String} object is returned. Otherwise, a
     * {@code String} object is returned that represents a character
     * sequence that is the concatenation of the character sequence
     * represented by this {@code String} object and the character
     * sequence represented by the argument string.
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
     * and trailing space removed, where space is defined
     * as any character whose codepoint is less than or equal to
     * {@code 'U+0020'} (the space character).
     * <p>
     * This method may be used to trim space (as defined above) from
     * the beginning and end of a string.
     *
     * @return  a string whose value is this string, with all leading
     *          and trailing space removed, or this string if it
     *          has no leading or trailing space.
     */
    public String trim();

    /**
     * Returns a string resulting from replacing all occurrences of
     * {@code oldChar} in this string with {@code newChar}.
     * <p>
     * If the character {@code oldChar} does not occur in the
     * character sequence represented by this {@code String} object,
     * then a reference to this {@code String} object is returned.
     * Otherwise, a {@code String} object is returned that
     * represents a character sequence identical to the character sequence
     * represented by this {@code String} object, except that every
     * occurrence of {@code oldChar} is replaced by an occurrence
     * of {@code newChar}.
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
     * the specified character. If a character with value
     * {@code ch} occurs in the character sequence represented by
     * this {@code String} object, then the index (in Unicode
     * code units) of the first such occurrence is returned. For
     * values of {@code ch} in the range from 0 to 0xFFFF
     * (inclusive), this is the smallest value <i>k</i> such that:
     * <blockquote><pre>
     * this.charAt(<i>k</i>) == ch
     * </pre></blockquote>
     * is true. For other values of {@code ch}, it is the
     * smallest value <i>k</i> such that:
     * <blockquote><pre>
     * this.codePointAt(<i>k</i>) == ch
     * </pre></blockquote>
     * is true. In either case, if no such character occurs in this
     * string, then {@code -1} is returned.
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
     * If a character with value {@code ch} occurs in the
     * character sequence represented by this {@code String}
     * object at an index no smaller than {@code fromIndex}, then
     * the index of the first such occurrence is returned. For values
     * of {@code ch} in the range from 0 to 0xFFFF (inclusive),
     * this is the smallest value <i>k</i> such that:
     * <blockquote><pre>
     * (this.charAt(<i>k</i>) == ch) {@code &&} (<i>k</i> &gt;= fromIndex)
     * </pre></blockquote>
     * is true. For other values of {@code ch}, it is the
     * smallest value <i>k</i> such that:
     * <blockquote><pre>
     * (this.codePointAt(<i>k</i>) == ch) {@code &&} (<i>k</i> &gt;= fromIndex)
     * </pre></blockquote>
     * is true. In either case, if no such character occurs in this
     * string at or after position {@code fromIndex}, then
     * {@code -1} is returned.
     *
     * <p>
     * There is no restriction on the value of {@code fromIndex}. If it
     * is negative, it has the same effect as if it were zero: this entire
     * string may be searched. If it is greater than the length of this
     * string, it has the same effect as if it were equal to the length of
     * this string: {@code -1} is returned.
     *
     * <p>All indices are specified in {@code char} values
     * (Unicode code units).
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
     * <p>The returned index is the smallest value {@code k} for which:
     * <pre>{@code
     * this.startsWith(str, k)
     * }</pre>
     * If no such value of {@code k} exists, then {@code -1} is returned.
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
     *         variable and may be zero.  The maximum number of arguments is
     *         limited by the maximum dimension of a Java array as defined by
     *         <cite>The Java&trade; Virtual Machine Specification</cite>.
     *         The behaviour on a
     *         {@code null} argument depends on the <a
     *         href="../util/Formatter.html#syntax">conversion</a>.
     *
     * @throws  java.util.IllegalFormatException
     *          If a format string contains an illegal syntax, a format
     *          specifier that is incompatible with the given arguments,
     *          insufficient arguments given the format string, or other
     *          illegal conditions.  For specification of all possible
     *          formatting errors, see the <a
     *          href="../util/Formatter.html#detail">Details</a> section of the
     *          formatter class specification.
     *
     * @return  A formatted string
     */
    public static String format(String format, Object... args);
}
```

### `java.lang.Object`

```java
package java.lang;

public class Object {
    /**
     * Indicates whether some other object is "equal to" this one.
     * <p>
     * Note that it is generally necessary to override the {@code hashCode}
     * method whenever this method is overridden, so as to maintain the
     * general contract for the {@code hashCode} method, which states
     * that equal objects must have equal hash codes.
     *
     * @param   obj   the reference object with which to compare.
     * @return  {@code true} if this object is the same as the obj
     *          argument; {@code false} otherwise.
     */
    public boolean equals(Object obj);

    /**
     * Returns a hash code value for the object. This method is
     * supported for the benefit of hash tables such as those provided by
     * {@link java.util.HashMap}.
     *
     * @return  a hash code value for this object.
     * @see     java.lang.Object#equals(java.lang.Object)
     * @see     java.lang.System#identityHashCode
     */
    @HotSpotIntrinsicCandidate
    public native int hashCode();

    /**
     * Returns a string representation of the object. In general, the
     * {@code toString} method returns a string that
     * "textually represents" this object. The result should
     * be a concise but informative representation that is easy for a
     * person to read.
     * It is recommended that all subclasses override this method.
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
     * @see java.lang.Cloneable
     */
    @HotSpotIntrinsicCandidate
    protected native Object clone() throws CloneNotSupportedException;

    /**
     * Causes the current thread to wait until it is awakened, typically
     * by being <em>notified</em> or <em>interrupted</em>.
     * <p>
     * In all respects, this method behaves as if {@code wait(0L, 0)}
     * had been called. See the specification of the {@link #wait(long, int)} method
     * for details.
     *
     * @throws IllegalMonitorStateException if the current thread is not
     *         the owner of the object's monitor
     * @throws InterruptedException if any thread interrupted the current thread before or
     *         while the current thread was waiting. The <em>interrupted status</em> of the
     *         current thread is cleared when this exception is thrown.
     * @see    #notify()
     * @see    #notifyAll()
     * @see    #wait(long)
     * @see    #wait(long, int)
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
     * ({@code '\u005Cu002D'}) to indicate a negative value or an
     * ASCII plus sign {@code '+'} ({@code '\u005Cu002B'}) to
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
         * this object.  Remaining lines represent data previously recorded by
         * the method {@link #fillInStackTrace()}.
         * The backtrace for a throwable with an initialized, non-null cause
         * should generally include the backtrace for the cause.
         * Note the presence of lines containing the characters {@code "..."}.
         * These lines indicate that the remainder of the stack trace for this
         * exception matches the indicated number of frames from the bottom of the
         * stack trace of the exception that was caused by this exception (the
         * "enclosing" exception).  This shorthand can greatly reduce the length
         * of the output in the common case where a wrapped exception is thrown
         * from same method as the "causative exception" is caught.
         */
        public void printStackTrace();
}
```

### `java.io.PrintWriter`

```java
package java.io;

public class PrintWriter extends Writer {
    /**
     * Creates a new PrintWriter, without automatic line flushing, with the
     * specified file name.  This convenience constructor creates the necessary
     * intermediate {@link java.io.OutputStreamWriter OutputStreamWriter},
     * which will encode characters using the {@linkplain
     * java.nio.charset.Charset#defaultCharset() default charset} for this
     * instance of the Java virtual machine.
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

public interface Cloneable {}
```

### `java.lang.Thread`

```java
package java.lang;

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

public class Executors {
    /**
     * Creates a thread pool that reuses a fixed number of threads
     * operating off a shared unbounded queue.  At any point, at most
     * {@code nThreads} threads will be active processing tasks.
     * If additional tasks are submitted when all threads are active,
     * they will wait in the queue until a thread is available.
     * If any thread terminates due to a failure during execution
     * prior to shutdown, a new one will take its place if needed to
     * execute subsequent tasks.  The threads in the pool will exist
     * until it is explicitly {@link ExecutorService#shutdown shutdown}.
     *
     * @param nThreads the number of threads in the pool
     * @return the newly created thread pool
     * @throws IllegalArgumentException if {@code nThreads <= 0}
     */
    public static ExecutorService newFixedThreadPool(int nThreads);

    /**
     * Creates a thread pool that creates new threads as needed, but
     * will reuse previously constructed threads when they are
     * available.  These pools will typically improve the performance
     * of programs that execute many short-lived asynchronous tasks.
     * Calls to {@code execute} will reuse previously constructed
     * threads if available. If no existing thread is available, a new
     * thread will be created and added to the pool. Threads that have
     * not been used for sixty seconds are terminated and removed from
     * the cache. Thus, a pool that remains idle for long enough will
     * not consume any resources. Note that pools with similar
     * properties but different details (for example, timeout parameters)
     * may be created using {@link ThreadPoolExecutor} constructors.
     *
     * @return the newly created thread pool
     */
    public static ExecutorService newCachedThreadPool();
}
```

### `java.util.concurrent.locks.Lock`

```java
package java.util.concurrent.locks;

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
