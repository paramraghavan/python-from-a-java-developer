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

[i](https://pymotw.com/3/importlib/)[mportlib - import modules dynamically](https://pymotw.com/3/importlib/)
### **Dump - print all the attributes of an object/class**
def dump(obj):

`  `for attr in dir(obj):

`    `print("obj.%s = %r" % (attr, getattr(obj, attr)))
### **Yield - use case process large file without reading the entire file at once**
yield is best used when you have a function that returns a sequence and you want to iterate over that sequence, but you do not need to have every value in memory at once.

For example, I have a python script that parses a large list of CSV files, and I want to return each line to be processed in another function. I don't want to store the megabytes of data in memory all at once, so I yield each line in a python data structure. So the function to get lines from the file might look something like:

def get\_lines(files):

`    `for f in files:

`        `for line in f:

`            `#preprocess line

`            `yield line

I can then use the same syntax as with lists to access the output of this function:

for line in get\_lines(files):

`    `#process line

but I save a lot of memory usage.

**ref:** <https://stackoverflow.com/questions/7883962/where-to-use-yield-in-python-best>
## **Print stack trace**
import traceback 

\# declaring and assigning array 
A = [1, 2, 3, 4]   
\# exception handling 
try: 
`    `value = A[5]       
except: 
`    `# printing stack trace 
`    `traceback.print\_exc()

\# out of try-except 
\# this statement is to show 
\# that program continues normally 
\# after an exception is handled 
print("end of program")

#----------------------------------------------------
## **Decorators in python - allows behavior to be added to an individual [object](https://en.wikipedia.org/wiki/Object_\(computer_science\) "Object (computer science)"), dynamically,**
## **ref: [https://realpython.com/lessons/timing-functions-decorators/**](https://realpython.com/lessons/timing-functions-decorators/)**
![](Aspose.Words.ca4ec84a-843e-4a78-b41f-95b43759fab0.001.png)

![](Aspose.Words.ca4ec84a-843e-4a78-b41f-95b43759fab0.002.png)

![](Aspose.Words.ca4ec84a-843e-4a78-b41f-95b43759fab0.003.png)


### **Elapsed time**
import time

start\_time = time.perf\_counter()

end\_time = time.perf\_counter()

runt\_time= end\_time - start\_time

print(f"Time elapsed  {end\_time:.4f} secs")
## **Yield and for loop**
pass keyword - kind of no-op operation
## **Exception**
Traceback module, TypeError as error

TypeError, KeyError, ValueError, catch all error → Exception



DataTypes

Tuple - immutable list. Example tuple = (3,5,6, "abc")

\*args

\*\*kwargs



def call():

`        `raise ValueError('record count failed to match')

`        `return



try:

`        `call()  

except ValueError as identifier:

`    `print(identifier) # prints the error message 'record count failed to match'





#The repr() function returns a printable representation of the given object.

msg = {'x':1,'y':2}

print(repr(msg))

output on console: "{'x': 1, 'y': 2}"





\# in the folloiwng case, The type(object) function returns the type of the object.

\# It could return a new type object based on the arguments passed

print(type(msg))

output on console: <class 'dict'>



#python dictionaries are key value pairs like  Hashmap in java, but can support mixed data types unlike java

\# dict. to json and back

student = {

`        `"name": "MArk",

`        `"rollnumber":123,

`        `"school": "python school"

`        `"misc": None,

`     `"msgdict": msg

}



student["name"] == "MArk"

student.get("last\_name") == KeyError

student.get("last\_name", "Unknown") == "Unknown"

student.keys()

student.values()


### **Classes** 
Inheritance and Compostion → <https://realpython.com/lessons/inheritance-composition-python-overview/>

<https://openbookproject.net/thinkcs/python/english3e/classes_and_objects_I.html>

#studentpy

students = []

class Student:

`        `school\_name = "Springfield Elementary"



`        `def \_\_init\_\_(self, name, student\_id=332):

`               `self.name = name

`               `self.student\_id = student\_id

`               `students.append(self)



`        `def \_\_str\_\_(self):

`               `return "Student " + self.name



`        `def get\_name\_capitalize(self):

`               `return self.name.capitalize()



`        `def get\_school\_name(self):

`               `return self.school\_name





mark = Student("Mark")

print(mark);





\---------------

#highschoolstudent.py





from student import Student



\# Student base class and HighSchoolStudent childor derived class

class HighSchoolStudent(Student):



`        `school\_name = "Springfield High School"



`        `def get\_school\_name(self):

`               `return "This is a High School student"



`        `def get\_name\_capitalize(self):

`               `original\_value = super().get\_name\_capitalize()

`               `return original\_value + "-HS"





#main.py

from hs\_student import \*



james = HighSchoolStudent("james")

print(james.get\_name\_capitalize())





output to console: James-HS


## **Unit test python**
<https://medium.com/@bezdelev/how-to-test-a-python-aws-lambda-function-locally-with-pycharm-run-configurations-6de8efc4b206> - won't work for us

pip install --trusted-host [pypi.org](http://pypi.org) python-lambda-local



[**Python Elasticbeanstalk support multiple request with PyFlask**](https://forums.aws.amazon.com/thread.jspa?threadID=232777)

[**Queue and Python**](https://www.geeksforgeeks.org/queue-in-python/)

[**Python and multithreading**](https://www.toptal.com/python/beginners-guide-to-concurrency-and-parallelism-in-python)

# Shallow vs deepcopy
https://thispointer.com/python-how-to-copy-a-dictionary-shallow-copy-vs-deep-copy/


