# **Python from a Java Developer**
## **Useful Links**
[**Python for Java developers**](https://lobster1234.github.io/2017/05/25/python-java-primer/)

**Global Variables**

- https://www.w3schools.com/python/python_variables_global.asp

[Learn Python](http://learnpython.org/)

[Python regular expression test](https://pythex.org/)

[Python Ternary Condition Expression](https://www.pythoncentral.io/one-line-if-statement-in-python-ternary-conditional-operator/)

<https://www.regextester.com/>

<https://pypi.org/>

<https://hackr.io/blog/best-python-books-for-beginners-and-advanced-programmers>

<http://greenteapress.com/thinkpython/thinkCSpy/thinkCSpy.pdf>

[Python and Dictionaries](http://learnpython.org/en/Dictionaries)

<https://docs.aws.amazon.com/glue/latest/dg/dev-endpoint-tutorial-pycharm.html>

[Boto3 & Python](https://realpython.com/python-boto3-aws-s3/) \*\* → [Boto3](https://boto3.amazonaws.com/v1/documentation/api/latest/index.html) is the name of the Python SDK for AWS. It allows you to directly create, update, and delete AWS resources from your Python scripts.

<https://boto3.amazonaws.com/v1/documentation/api/latest/guide/quickstart.html>

<https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html> - Access id/key

**Show installed package →** pip show boto3

<https://app.pluralsight.com/library/courses/python-getting-started/table-of-contents> → basic python

**Virtual Environment :**
There is something in the Python world called a virtual environment. What is it exactly? Well, virtual environments allow you to set up independent Python environments when you're working on your Python application. Imagine you're working on a web app. The web app you're working on for your client uses Django 1. 8 even though that's not the latest version, but it is the latest long-term support release. However, you also want to have Django 1. 11 installed on your machine because you want to get your hands dirty, maybe check out that new admin interface. Either way, you cannot have both versions of Django installed on your machine. There's going to be a version conflict, so you can only have one of those twoinstalled. But what you can do is simply create two isolated Python environments. In each one of these isolated environments you can install whatever packages you want completely independent of each other, and they both live on the same machine. Heck, you can even use the different Python interpreter versions as well. On my personal machine, I have a virtualenvironment with Python 3. 6 for this course, then Python 3. 5. 1 for my personal web project because that's the Python version that my web server provider has. Then I have one for version 2. 7 and so on. It is fairly common to have many virtual environments set up on your machine, especially if you're working on multiple applications. They each have their own packages, and they don't care about each other at all. Now this may all sound silly and unnecessary to you at this point, but when you start working on an even slightly more complicated Python application, you will really appreciate the power and ease of use of virtual environments. To start using a virtual environment, you first need to install thevirtualenv package using pip. So just run pip and install virtualenv. From then on, the virtualenv command will be globally available in your terminal or PowerShell. Creating a virtual environment is super simple. Just type virtualenv and then followed by the environment name. The environment name can be whatever you want. For example, I created a virtualenv for this course called Pluralsight Getting Started. Now that's a mouthful. I usually name my virtual environments according to the project name. You can specify the Python version that you want your virtualenv to use by passing the --python flag and putting the path to your Python executable. Also, here's a tip: It's totally okay to keep all of your creative virtual environments in one folder. For example, I have a folder in my home directory called venvs. This is where all my of virtual environments live. This is perfectly fine. Finally, when you're done creating an environment, you need to activate it. When the environment was created, it created a folder with the same name as the virtual environment name and several subfolders. In order to activate the virtual environment, simply type source, then the path to your virtual environment folder, followed by the /bin/activate. If successful, your terminal or PowerShell prompt should be prefixed with the virtual environment name. Now when your virtual environment is activated, if you install packages using pip, it will only be installed to that specific virtual environment. It will not be available outside of it even in the global Python environment. Similarly, when you use the Python command directly, it will use the Python interpreter that you created for that virtual environment. To leave the virtual environment, simply type deactivate while your virtual environment is active. PyCharm is also able to work with virtual environments and can help you set them up as well. Simply search for the interpreter options in the PyCharm settings. Speaking of PyCharm, let's explore another great feature that it comes with, and that's debugging our Python code.

[**https://www.pyinstaller.org/](https://www.pyinstaller.org/)**, pyinstaller** - is a Python package that allows us to create binary executable files from our Python program. It is cross-platform so it will create the. exe file for Windows and a. app file for Mac. It also works under Linux 2 and a gazillion other platforms.

pyinstaller --onefile ./yourpythonfile.py → this creates one single file as exe as opposed to an small exe files and other dependent files.

**Setup Wizard**

**Inno Setup → jrsoftware.org**

[@staticmethod](https://stackabuse.com/pythons-classmethod-and-staticmethod-explained/)

[importlib - import modules dynamically](https://pymotw.com/3/importlib/) - importlib is kind of Class.forName() in java.
<pre>
  def get_class( kls ):
  	parts = kls.split('.')
  	module = ".".join(parts[:-1])
  	m = __import__( module )
  	for comp in parts[1:]:
  	m = getattr(m, comp)            
  	return m
  	
  >>> D = get_class("datetime.datetime")
  >>> D
  <type 'datetime.datetime'>
  >>> D.now()
  datetime.datetime(2009, 1, 17, 2, 15, 58, 883000)
  >>> a = D( 2010, 4, 22 )
  >>> a
  datetime.datetime(2010, 4, 22, 0, 0)
  
  We're using __import__ to import the module that holds the class, which required that we first extract 
  the module name from the fully qualified name. Then we import the module:
  
  m = __import__( module )
  In this case, m will only refer to the top level module,
  
  For example, if your class lives in foo.baz module, then m will be the module foo
  We can easily obtain a reference to foo.baz using getattr( m, 'baz' )
  
  To get from the top level module to the class, have to recursively use gettatr on the parts of the class name
  
  Say for example, if you class name is foo.baz.bar.Model then we do this:
  
  m = __import__( "foo.baz.bar" ) #m is package foo
  m = getattr( m, "baz" ) #m is package baz
  m = getattr( m, "bar" ) #m is module bar
  m = getattr( m, "Model" ) #m is class Model
  This is what's happening in this loop:
  
  for comp in parts[1:]:
      m = getattr(m, comp)    
  At the end of the loop, m will be a reference to the class. This means that m is actually the class itslef, you can do for instance:
</pre>
[above ref](https://stackoverflow.com/questions/452969/does-python-have-an-equivalent-to-java-class-forname)
### **Dump - print all the attributes of an object/class**
<pre>
    def dump(obj):
      for attr in dir(obj):
        print("obj.%s = %r" % (attr, getattr(obj, attr)))
</pre>

### **Yield - use case process large file without reading the entire file at once**
<pre>
	#yield is best used when you have a function that returns a sequence and you want to iterate over that sequence, but you do not need to have every value in memory at once.
	#For example, I have a python script that parses a large list of CSV files, and I want to return each line to be processed in another function. I don't want to store the megabytes of data in memory all at once, so I yield each line in a python data structure. So the function to get lines from the file might look something like:
	def get_lines(files):
		for f in files:
			for line in f:
				#preprocess line
				yield line
				
				
	#I can then use the same syntax as with lists to access the output of this function:
	for line in get_lines(files):
		#process line
	#but u save a lot of memory usage.
</pre>
**ref:** <https://stackoverflow.com/questions/7883962/where-to-use-yield-in-python-best>
## **Print stack trace**
<pre>
    import traceback 
      
    # declaring and assigning array 
    A = [1, 2, 3, 4]   
    # exception handling 
    try: 
        value = A[5]       
    except: 
        # printing stack trace 
        traceback.print_exc()
    # out of try-except 
    # this statement is to show 
    # that program continues normally 
    # after an exception is handled 
    print("end of program")
</pre>

## A **decorator** is a design pattern  that allows a user to add new functionality to an existing object without modifying its structure. 
- [decorators link1](https://realpython.com/lessons/timing-functions-decorators/)
- [decorators link2](https://www.datacamp.com/community/tutorials/decorators-python)
- [@see code sample](https://github.com/paramraghavan/python-from-a-java-developer/blob/main/src/decorators/sample.py)


![](Aspose.Words.ca4ec84a-843e-4a78-b41f-95b43759fab0.001.png)

![](Aspose.Words.ca4ec84a-843e-4a78-b41f-95b43759fab0.002.png)

![](Aspose.Words.ca4ec84a-843e-4a78-b41f-95b43759fab0.003.png)


### **Elapsed time**
import time

start\_time = time.perf\_counter()

end\_time = time.perf\_counter()

runt\_time= end\_time - start\_time

print(f"Time elapsed  {end\_time:.4f} secs")
ref: https://www.geeksforgeeks.org/timing-functions-with-decorators-python/

## **Yield and for loop**
pass keyword - kind of no-op operation
## **Exception**
Traceback module, TypeError as error

TypeError, KeyError, ValueError, catch all error → Exception



DataTypes

Tuple - immutable list. Example tuple = (3,5,6, "abc")

\*args

\*\*kwargs

<pre>
    def call():
        raise ValueError('record count failed to match')
        return
    
    try:
        call()	
    except ValueError as identifier:
        print(identifier) # prints the error message 'record count failed to match'
    
    
    #The repr() function returns a printable representation of the given object.
    msg = {'x':1,'y':2}
    print(repr(msg))
    output on console: "{'x': 1, 'y': 2}"
    
    
    # in the folloiwng case, The type(object) function returns the type of the object.
    # It could return a new type object based on the arguments passed
    print(type(msg))
    output on console: <class 'dict'>
    
    #python dictionaries are key value pairs like  Hashmap in java, but can support mixed data types unlike java
    # dict. to json and back
    student = {
        "name": "MArk",
        "rollnumber":123,
        "school": "python school"
        "misc": None,
         "msgdict": msg
    }
    
    student["name"] == "MArk"
    student.get("last_name") == KeyError
    student.get("last_name", "Unknown") == "Unknown"
    student.keys()

</pre>

### **Classes** 
Inheritance and Compostion → <https://realpython.com/lessons/inheritance-composition-python-overview/>

<https://openbookproject.net/thinkcs/python/english3e/classes_and_objects_I.html>

#studentpy
<pre>
    students = []
    class Student:
        school_name = "Springfield Elementary"
    
        def __init__(self, name, student_id=332):
            self.name = name
            self.student_id = student_id
            students.append(self)
    
        def __str__(self):
            return "Student " + self.name
    
        def get_name_capitalize(self):
            return self.name.capitalize()
    
        def get_school_name(self):
            return self.school_name
    
    
    mark = Student("Mark")
    print(mark);
    
    
    ---------------
    #highschoolstudent.py
    
    
    from student import Student
    
    # Student base class and HighSchoolStudent childor derived class
    class HighSchoolStudent(Student):
    
        school_name = "Springfield High School"
    
        def get_school_name(self):
            return "This is a High School student"
    
        def get_name_capitalize(self):
            original_value = super().get_name_capitalize()
            return original_value + "-HS"
    
    
    #main.py
    from hs_student import *
    
    james = HighSchoolStudent("james")
    print(james.get_name_capitalize())
    
    
    output to console: James-HS

</pre>

## instanceOf <> isInstance check

age = isinstance(51,int)
print("age is an integer:", age)
>Output: age is an integer: True

pi = isinstance(3.14,float)
print("pi is a float:", pi)
>Output: pi is a float: True

message = isinstance("Hello World",str)
print("message is a string:", message)
>Output: message is a string: True

my_dict = isinstance({"A":"a", "B":"b", "C":"c", "D":"d"},dict)
print("my_dict is a dict:", my_dict)
>Output: my_dict is a dict: True

**Reference**: https://www.guru99.com/type-isinstance-python.html#8

Python for each
---------------
- https://stackoverflow.com/questions/47304818/pyspark-foreach-with-arguments
<pre>
def f(x,arg1,arg2,arg3): 
    print(x*arg1+arg2+arg3)

from functools import partial

sc.parallelize([1, 2, 3, 4, 5]).foreach(
    partial(f, arg1=11, arg2=21, arg3=31)
 )
</pre>

## **Unit test python**
<https://medium.com/@bezdelev/how-to-test-a-python-aws-lambda-function-locally-with-pycharm-run-configurations-6de8efc4b206> - won't work for us

pip install --trusted-host [pypi.org](http://pypi.org) python-lambda-local



[**Python Elasticbeanstalk support multiple request with PyFlask**](https://forums.aws.amazon.com/thread.jspa?threadID=232777)

[**Queue and Python**](https://www.geeksforgeeks.org/queue-in-python/)

[**Python and multithreading**](https://www.toptal.com/python/beginners-guide-to-concurrency-and-parallelism-in-python)

# Shallow vs deepcopy
https://thispointer.com/python-how-to-copy-a-dictionary-shallow-copy-vs-deep-copy/


