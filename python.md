# Python 101 - Everything in python is an object (has methods and values)

# Table of Contents
1. [Data Types](#types)
2. [Data Structures](#structures)
3. [Conditional Statements](#conditional)
4. [Comprehension](#comprehension)
5. [Exception Handling](#exception)
6. [Working with Files](#files)
7. [Arguments](#args)
8. [Classes](#classes)
9. [Python Standard Libraries](#libraries)
10. [SQL Alchemy](#sqlalchemy)
## 1. Single-item data types (int, string, float, bools) <a name="types"></a>
### Casting (Conversion of data types)
```
num = 123
string = str(num)

a = "123"
b = int(a)
````
### Single-item data types are immutable (they can not be changed)
```
string = "abc"
string[0] = "d"
TypeError: 'str' object does not support item assignment

num = 123
num[0] = 4
TypeError: 'int' object is not subscriptable
```
### Concatenation (combination of two things)
```
string1 = "hello"
string2 = "world"
string3 = string1 + ' ' + string2
```
### Slicing [start : stop ] (start includes index, stop does not)
```
string = "I like Python!"
string[2:6] will produce 'like'
```
### Formatting AKA Substitution (substituting values into a base )
```
my_string = "I like %s" % "Python" produces 'I like Python'

var = "cookies"
my_string = "I like %s" % var produces 'I like cookies'

int_string = "%i + %i = %i" % (1,2,3) produces 1 + 2 = 3

float_string = "%f" % (1.23) produces 1.230000

float_string2 = "%.2f" % (1.23) produces 1.23

float_string3 = "%.2f" % (1.237) produces 1.24
```
### String Prefixes (change how the string is interpreted)
```
f: formatted string literal (a way to embedded expressions)
greeting = f"Hello, {name}. You are {age} years old."

r: raw string (to avoid \\ being taken literal)
raw_path = r"C:\Users\Alice\Documents"

b: byte string (handle binary data)
byte_data = b"\x48\x65\x6c\x6c\x6f"  # Hexadecimal representation of "Hello"

fr: combined raw and formatted string literal
message = fr"{user}, your folder is located at {path}\Documents"
```


## 2. Lists, Tuples and Dictionaries (Heterogeneous = can store objects of different types) <a name="structures"></a>
## Lists (lists are mutable)
```
my_list = [1,2,4]
my_list[2] = 3
my_list.append(4)
```
### Heterogeneous (can store objects of different types)
```
[] or list([])

my_list = [1, "yes", 2, 2.70]
my_list = list((1, "yes", 2, 2.70))
```
### Nested vs Concationation
```
list1 = [1,2,3]
list2 = ["a", "b", "c"]

nested = [list1, list2]

concatination = list1 + list2
```
## Tuples (tuples are immutable)
```
() or tuple([])

my_tuple = (1,2,3)
my_tuple[0]
TypeError: 'tuple' object does not support item assignment
```
### Assignment
```
x = (1) produces a int 1
x = (1,) produces a tuple due to the comma
```
## Sets
Unlike lists and tuples, sets cannot contain duplicate and unordered values. <br>
```
my_list = [1,2,4,3,5,5]
my_set = set(my_list)
```
## Dictionaries (hash table / hash mapping) (set of unorderd key-value pairs)
![](images/dict.PNG)
```
{} or dict()

my_dict = {1: "one", 2: "two", 3: "three"}
```
### Manipluation (items can only be found via the key)
```
for i in range my_dict .values .items .keys

for key in my_dict

my_dict[4] = "four"

my_dict.pop(4)
```
### Check for if key exists (boolean)
```
print(2 in my_dict)
```

## 3. Conditional statements (checks if true or false) <a name="conditional"></a>
```
if, elif, else
if x not in
if x in
```
### if name == main
- This tells Python that you only want to run the following code if this program is executed as a standalone file. <br>
- Whenever you create a Python script, you create a Python module. <br>
- When you do import a module, it will not run the code that’s under the conditional because __name__ will no longer equal “__main__”. 
```
if __name__ == "__main__":
```


## 4. Comprehension (create new sequences from existing ones) <a name="comprehension"></a>
### List comprehesnion
```
x = [i for i in range(10)]
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```
### Casting in list comprehensions
```
x = ['1', '2', '3', '4', '5']
y = [int(i) for i in x]
[1, 2, 3, 4, 5, 6, 7, 8, 9]
```
### Nested list comprehension
```
x = [[1,2,3], [4,5,6], [7,8,9]]
y = [num for elem in x for num in elem]
[1, 2, 3, 4, 5, 6, 7, 8, 9]
```
### Dictionary comprehension
```
my_dict = {i: i for i in range(10)}
{0: 0, 1: 1, 2: 2, 3: 3, 4: 4, 5: 5, 6: 6, 7: 7, 8: 8, 9: 9}

my_dict = {1: "yes", 2: "no", 3: "ok"}
swap_key_val_dict = {v: k for k, v in my_dict.items()}

filtered_dict = {k: v for k, v in my_dict.items() if k > 2}
{3: 'ok'}

calculation_dict = {k: v**2 for k, v in my_dict.items()}
```
### Set comprehension
```
my_list = [1,2,3,4,4]
my_set = {x for x in my_list}
{1, 2, 3, 4}
```


## 5. Exception Handling (try/except) <a name="exception"></a>
### Common Exceptions
```
Exception (all built off of)
AttributeError (attribute refrence or assignment fails)
IOError (raised when an I/O fails)
ImportError (rasied when a module is not found)
IndexError (raised when accessing an out of range index)
KeyError (raised when a key in dict is not found)
KeyboardInterrupt (raied when the user hits the intterupt key (CRTL C))
NameError (raised when a local or global name is not found)
OSError (raised when a function returns a system-related error)
SyntaxtError (raised when incorrect syntax is used)
TypeError (raised when an opperation or function is applied to an innapropriate type)
ValueError (raised when a function has an innapropriate value)
ZeroDivisionError (raised when the second argument of a division or modulo operation is zero) e.g. 1/0
```
### Excepts
```
try:
    something
except (errortype):
    do something if try didnt work
```
### Catch single exceptions
```
my_dict = {"a":1, "b":2, "c":3}
try:
    value = my_dict["d"]
except KeyError:
    print("this key does not exist")
```
### Catch multiple exceptions
```
try:
    value = my_dict["d"]
except (KeyError, IndexError):
    print("An KeyError or IndexError occured")
```


## 6. Working with files <a name="files"></a>
### Read file (for reading)
```
handle = open("test.txt", "r")
or
handle = open(r"C:\User\etc...", "r")
```
### Open file (Closing the file will help save memory bugs)
```
data = handle.read()
print(data)
handle.close()
```
### Iteration read file (read file until 1024 bytes at a time == 1 Kilobyte)
```
while True:
    data = handle.read(1024)
    print(data)
    if not data:
        break
```
### Write file (if the file already exists, it will be overwritten with no warning)
```
handle = open("test.txt", "w")
handle.write ("changing the text in the file")
handle.close()
```
### with operator aka context manager (automatically close the file)
```
handle = open("test.txt")
is the same as
with open("test.txt") as file handler:
```
### Catching errors
```
try:
    with open("test.txt") as file_handler:
        for line in file_handler:
            print(line)
except IOError:
    print("An IOError occured")
```

## 7. *args and **kwargs (allow functions to accept an arbitrary number of arguments) <a name="args"></a>
### args (arguments)
```
def fun(*args):
    return sum(args)

print(fun(5,10,15))
```
### kwargs (keyword arguments)
```
def fun(**kwargs):
    for k, val in kwargs.items():
        print(k, val)

fun(a=1, b=2, c=4)
```
### Global variables (variable shared throughout functions)
```
def function_a():
    global a
    a = 1
    b = 2
    return a+b

def function_b():
    c = 3
    return a+c

print(function_a())
print(function_b())
```


## 8. Classes (A class is a blueprint of an object) <a name="classes"></a>
- Everything in python is an object as it has methods and values
- Lets take this string for example
- Using dir() we can find the methods available for the string
- A string is based on a class and x is an instance of that class
```
x = "mike"
dir(x)
['__add__', '__class__', '__contains__', '__delattr__', '__doc__', '__eq__',
'__format__', '__ge__', '__getattribute__', '__getitem__', '__getnewargs__',
'__getslice__', '__gt__', '__hash__', '__init__', '__le__', '__len__', '__lt__',
'__mod__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__',
'__rmod__', '__rmul__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__',
'_formatter_field_name_split', '_formatter_parser', 'capitalize', 'center', 'count',
'decode', 'encode', 'endswith', 'expandtabs', 'find', 'format', 'index', 'isalnum',
'isalpha', 'isdigit', 'islower', 'isspace', 'istitle', 'isupper', 'join', 'ljust',
'lower', 'lstrip', 'partition', 'replace', 'rfind', 'rindex', 'rjust', 'rpartition',
'rsplit', 'rstrip', 'split', 'splitlines', 'startswith', 'strip', 'swapcase', 'title',
'translate', 'upper', 'zfill']
```
### Creating a class
- Class name should start with capital
- A function changes to a method when in a class
- Every method must have at least one argument (i.e self)
```
class Vehicle:

    def __init__(self):
    """constructor"""
        pass
```
### Attributes and methods
- Attributes belong to the class
- They describe the vehicle
- There are also two methods which belong to the class
```
class Vehicle:

    def __init__(self, colour):
        """constructor / initialised"""
        self.colour = colour
        self.doors = doors
        self.tires = tires
    
    def brake(self):
        """stop the car"""
        return "Braking"

    def drive(self):
        "Drive the car"
        return "Driving"
```
### self ()
- self is used in a class to refer to itself
- Its a way to tell one instance from another
```
class Vehicle:
    """docstring"""

    def __init__(self, color, doors, tires, vtype):
        """Constructor"""
        self.color = color
        self.doors = doors
        self.tires = tires
        self.vtype = vtype

    def brake(self):
        """
        Stop the car
        """
        return "%s braking" % self.vtype

    def drive(self):
        """
        Drive the car
        """
        return "I'm driving a %s %s!" % (self.color, self.vtype)

if __name__ == "__main__":
    car = Vehicle("blue", 5, 4, "car")
    truck = Vehicle("red", 3, 6, "truck")
```
### Subclasses (inherit the methods from the parent class and can overide them)
- You inherit the attributes from the parent class
```
class Car(Vehicle):
    """
    The Car class
    """

    def brake(self):
        """
        Override brake method
        """
        return "The car class is breaking slowly!"

if __name__ == "__main__":
    car = Car("yellow", 2, 4, "car")
    car.brake()
    'The car class is breaking slowly!'
    car.drive()
    "I'm driving a yellow car!"
```


## 9. Python standard libraries (modules that come with python) <a name="libraries"></a>
- A module is a set of pre-written code with instructions
### Introspection modules
```
type() - object type
type(123)

dir() - tells what attributes and methods there are in the object
dir("test")

help() - provides instructions and options which you can then search
```
### CSV modules (reading)
```
import csv

csv_path = "TB_data_dictionary_2014-02-26.csv"
with open(csv_path, "r") as f_obj:
    for line in f_obj:
        print(line)
```
### Configparser
Used for storing your application’s settings or even your operating system’s settings
```
import configparser

def createConfig(path):
    """
    Create a config file
    """
    config = configparser.ConfigParser()
    config.add_section("Settings")
    config.set("Settings", "font", "Courier")
    config.set("Settings", "font_size", "10")
    config.set("Settings", "font_style", "Normal")
    config.set("Settings", "font_info",
               "You are using %(font)s at %(font_size)s pt")

    with open(path, "w") as config_file:
        config.write(config_file)


if __name__ == "__main__":
    path = "settings.ini"
    createConfig(path)
```
### Logging (record and log events that happen in the program)
![](images/logging.PNG)
<br>
Level selects where the logging message will commence from
```
import logging

# add filemode="w" to overwrite
logging.basicConfig(filename="sample.log", filemode="w", level=logging.DEBUG)

logging.debug("This is a debug message")
logging.info("Informational message")
logging.error("An error has happened!")
```
![](images/logvsprint.PNG)
### OS module (operating system, bridge between python and os)
```
import os
```
### os name
```
os.name

'nt'
```
### os environ (aka mapping object which returns a dictionary of the user enviroment variables)
```
os.environ

{'ALLUSERSPROFILE': 'C:\\ProgramData',
 'APPDATA': 'C:\\Users\\mike\\AppData\\Roaming',
 'CLASSPATH': '.;C:\\Program Files\\QuickTime\\QTSystem\\QTJava.zip',
 'COMMONPROGRAMFILES': 'C:\\Program Files\\Common Files',
 'COMPUTERNAME': 'MIKE-PC' ......
```
### os getenv (same as environ but will return none instead of error is env doesnt exist)
```
os.getenv('APPDATA')
```
### os getcwd (get working directory)
```
os.getcwd()

C:\Users\Kyle\Documents\Sparta\pre-assignment\python
```
### os mkdir (make directory/ folder)
```
os.mkdir('test_folder')
```
### os remove (remove file)
```
os.remove("test.txt")
```
### os rmdir (remove directory)
```
os.rmdir('test_folder')
```
### os rename (rename directory or file)
```
os.rename("test.txt", "pytest.txt")
```
### os path exists (check is path exists bool)
```
os.path.exists(path)
```
## Sqllite module (sql database engine)
- self-contained
- server-less
- config free
- can create any sqllite database using python
### Create database and table
```
import sqlite3

connection = sqlite3.connect("mydb.db")

cursor = connection.cursor()

# create table
cursor.execute("""CREATE TABLE albums
                (title text, artists text, release_date text,
                publisher text, media_type text)
               """)
```
### Insert data
```
# insert some data
cursor.execute("""INSERT INTO albums
                  VALUES ('Glow', 'Andy Hunter', '7/24/2012',
                          'Xplore Records', 'MP3')"""
               )

# save data to database
conn.commit()
```
### Insert multiple data (more secure way)
- Paramatarised query (?,?,?,?)
- handles the variable substitution
- safe way to avoid sql injection attacks by giving the variable name
```
# insert multiple records using the more secure "?" method
albums = [('Exodus', 'Andy Hunter', '7/9/2002', 'Sparrow Records', 'CD'),
          ('Until We Have Faces', 'Red', '2/1/2011', 'Essential Records', 'CD'),
          ('The End is Where We Begin', 'Thousand Foot Krutch', '4/17/2012', 'TFKmusic', 'CD'),
          ('The Good Life', 'Trip Lee', '4/10/2012', 'Reach Records', 'CD')]
cursor.executemany("INSERT INTO albums VALUES (?,?,?,?,?)", albums)
conn.commit()
```
### Update records
```
sql = """
UPDATE albums
SET artist = 'John Doe'
WHERE artist = 'Andy Hunter'
"""
cursor.execute(sql)
conn.commit()
```
### Deleting records
```
sql = """
DELETE FROM albums
WHERE artist = 'John Doe'
"""
cursor.execute(sql)
conn.commit()
```
### Query records
```
sql = "SELECT * FROM albumns WHERE artist = 'Ice Cube'"
cursor.execute(sql)
print(cursor.fetchall() or fetchone())
```


## Datetime and time module (year, month, day, hours, minute, second)
```
import datetime
```
### datetime.date (date)
```
current_date = datetime.date(2025, 10, 8)
or
current_date = datetime.date.today()
```
### datetime.datetime (date and time (hour, minute, seconds))
```
current_date_time = datetime.datetime(2025, 10, 8, 12, 37, 24)
or 
current_date_time = datetime.datetime.today()
or
current_date_time = datetime.datetime.now()
```
### query date and time
```
current_day.year
current_day.month
current_day.day
current_day.hour
current_day.minute
current_day.second
```
### datetime.timedelta (time duration, type: timedelta)
```
now = datetime.datetime.now()
then = datetime.datetime(2014, 4, 30)
delta = now - then
```
### time
```
import time
```
### time.gmtime (epoch (the point which time starts))
```
time.gmtime(0)

time.struct_time(tm_year=1970, tm_mon=1, tm_mday=1, tm_hour=0, tm_min=33, tm_sec=20, tm_wday=3, tm_yday=1, tm_isdst=0)
```
### time.ctime (covert seconds into date)
```
time.ctime(19535636343)

Wed Jan 21 21:39:03 2589
```
### time.sleep (used to suspend execution)
```
print("second 1")
time.sleep(5)
print("second 6")
```
### time.time (return the time in seconds since epoch)
```
time.time()
1759928406.8725529
```
### Python debugger (test function)
```
import pdb
pdb.run('testing.main()')
```
### Urlib request (module used to open URLS)
```
import urlib.request

request_url = urlib.request.urlopen("mywebsite.com")
```
### Requests (pythonic replacement for urlib)
```
import requests

r = requests.get("mywebsite.com")
```
### request options
```
dir(r)

['__attrs__', '__bool__', '__class__', '__delattr__', '__dict__',
'__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__',
'__getstate__', '__gt__', '__hash__', '__init__', '__iter__', '__le__', '__lt__',
'__module__', '__ne__', '__new__', '__nonzero__', '__reduce__', '__reduce_ex__',
'__repr__', '__setattr__', '__setstate__', '__sizeof__', '__str__', '__subclasshook__',
'__weakref__', '_content', '_content_consumed', 'apparent_encoding', 'close',
'connection', 'content', 'cookies', 'elapsed', 'encoding', 'headers', 'history',
'iter_content', 'iter_lines', 'json', 'links', 'ok', 'raise_for_status', 'raw',
'reason', 'request', 'status_code', 'text', 'url']
```
## 10.SQLAlchemy (Object-Relational Mapper) <a name="sqlalchemy"></a>
### Engine Configuration
![](images/engine.PNG)
### DBAPI (Python Database API Specification)
- Low level API
- Defines usage pattern for all database connection packages
- SQLAlchemy’s dialect system is constructed around the operation of the DBAPI
```
postgresql+psycopg2://@localhost/test refers to the psycopg2 DBAPI/dialect combination

mysql+mysqldb://@localhost/test refers to the MySQL for Python DBAPI/dialect combination
```
### Engine (describes how to talk to a specific kind of database/ DBAPI)
- A single engine manages many individual DBAPI connections
- The engine is most effecient when created just once at the module level
```
from sqlalchemy import create_engine

engine = create_engine("mysql+mysqldb://scott:tiger@hostname/dbname")
```
### Engine Connection (handles the connection)
- most basic function of the engine is to provide access to a connection
- this can then invoke SQL statements
```
from sqlalchemy import text

with engine.connect() as connection:
    result = connection.execute(text("SELECT song FROM albums"))
    for row in result:
        print(row)
```