Download Link: https://assignmentchef.com/product/solved-csci1933-project5-hash-table-implementation
<br>
<h1></h1>

<ul>

 <li>The keys that we will use for this project will all be Strings which are “tokens.”</li>

 <li>For this project, a “token” will be defined as any sequence of characters (other than the white space characters: tab, space, newline) delimited by one or more white space characters. For example, the following are all tokens:</li>

</ul>

-123.34 computer and result. *hello abc) {}

( x x,y

<ul>

 <li>Do NOT maintain duplicate entries of a key in your hash table. In other words, if a token occurs multiple times, only put it in the hash table once.</li>

</ul>

WHAT TO DO

What To Do

<h1>1           Reading Tokens</h1>

To make testing of your hash table quick and simple, it is best to start with a way to easily read symbols (or tokens) from a file. The file TextScan.java has has been provided for you to use (or modify) in order to read tokens from an arbitrary file. The main() driver method in TextScan.java reads (and displays) all tokens found in the file specified on the command line when running TextScan. Try it on some arbitrary file–for example, itself. You may borrow TextScan.java and modify it to meet the requirements of this project, but if you do, be sure to properly credit the source within your program.

<h1>2           Build a Hash Table</h1>

Build a hash table of an “optimal” length that you choose (around 100 for now). The hash table implementation should use “chaining” (as discussed in lecture) to handle collided elements.

The hash table can be an array of NGen<em>&lt;</em>T<em>&gt;</em>. (Recall NGen<em>&lt;</em>T<em>&gt; </em>is the generic linked list node class.) To keep things simple, and since our purpose here is to develop good hash functions, the only two public methods for your Hash class are:

public void add(T item) // adds item to the hash table public void display() // displays the hash table or stats about the hash

// table in order to determine how well the hash // function works

<h1>3           Display a Hash Table</h1>

It will be necessary to print out the contents of your hash table so that we can tell how well your hash functions are working. Write a method:

public void display()

that will display each location in your hash table along with the number of keys that “hashed” to that location. You should also report the lengths of the longest and shortest chains (to make it easier to check the performance of larger tables).

<h1>4           Finding a “Good” Hash Function</h1>

Write several hash functions: private int hash(T key)

<ol start="5">

 <li>PERFORMANCE</li>

</ol>

that attempt to distribute tokens “evenly” across the hash table. This function will be called in the add() method, and should return an index of the NGen<em>&lt;</em>T<em>&gt; </em>array where the item will be placed. Sample files have been provided for you to test your hash table and hash functions. (See proverbs.txt, canterbury.txt, gettysburg.txt, and that bad.txt). You may also use files of your own. Note that the hash table does not need to grow to handle larger files, but the hash function should distribute the collided values evenly across the hash table. Once you have a good hash function, keep it to yourself! A good hash function is the key to an effective hash table, and it can give you a competitive performance edge. However, in your program comments you should explain how your hash function works. IMPORTANT NOTE: Do NOT attempt to “size” your table to the amount of data. In general, you will not know the amount of data. So, make your table relatively small (a prime number around 100). Again, a good hash function will evenly distribute the keys across the length of the table.

<h1>5           Performance</h1>

When you have Step 4 working, write some code to let you know how well your hash function distributed the keys over the table. This could be as simple as displaying the number of items chained at each location in the hash table. Do not expect a perfect hash function, but a good one will have very few unused locations, and no locations will have a chain of collided elements that is much longer than the others. We would like to see most chains of collided elements at about the same length.

<h1>6           A Specific Hash Table</h1>

In some cases, the data that will go into the hash table is known in advance. One such example of this is the reserved words for a programming language. In the file “keywords” are the 50 reserved keywords in the Java programming language. With some effort, it should be possible to map all the keywords (without collision) to a hash table. Try to do this. Again, keep your hash function to yourself, but explain how it works in your program comments. What is the smallest your hash table can be without having any collisions?