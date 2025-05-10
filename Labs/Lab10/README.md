# Engineering Design VI `CPE 322-A`
## Lab 10 — Blockchain
---

- **`blockchain`**
  - [`random hash function`](#1)
  - [`secure hash algorithm`](#2)
  - [`tiniest blockchain`](#3)
  - [`block mine`](#4)
- [`blockchain app`](#5)


To go to the postscript, click [`HERE`](#100)

---

```
PS C:\Users\mrdan> cd iot
PS C:\Users\mrdan\iot> cd *10
PS C:\Users\mrdan\iot\lesson10> cat hash_value.py
"""
https://docs.python.org/3/using/cmdline.html#envvar-PYTHONHASHSEED
If PYTHONHASHSEED is not set or set to random, a random value is used to to seed the hashes of str and bytes objects.
If PYTHONHASHSEED is set to an integer value, it is used as a fixed seed for generating the hash() of the types covered by the hash randomization.
Its purpose is to allow repeatable hashing, such as for selftests for the interpreter itself, or to allow a cluster of python processes to share hash values.
The integer must be a decimal number in the range [0,4294967295]. Specifying the value 0 will disable hash randomization.

https://www.programiz.com/python-programming/methods/built-in/hash
hash(object) returns the hash value of the object (if it has one). Hash values are integers.
They are used to quickly compare dictionary keys during a dictionary lookup.
Numeric values that compare equal have the same hash value even if they are of different types, as is the case for 1 and 1.0.
For objects with custom __hash__() methods, note that hash() truncates the return value based on the bit width of the host machine.
"""

# hash for integer unchanged
print('The hash for 1 is:', hash(1))

# hash for decimal
print('The hash for 1.0 is:',hash(1.0))
print('The hash for 3.14 is:',hash(3.14))

# hash for string
print('The hash for Python is:', hash('Python'))

# hash for a tuple of vowels
vowels = ('a', 'e', 'i', 'o', 'u')
print('The hash for a tuple of vowels is:', hash(vowels))

# hash for a custom object
class Person:
    def __init__(self, age, name):
        self.age = age
        self.name = name
    def __eq__(self, other):
        return self.age == other.age and self.name == other.name
    def __hash__(self):
        return hash((self.age, self.name))
person = Person(23, 'Adam')
print('The hash for an object of person is:', hash(person))
PS C:\Users\mrdan\iot\lesson10> python hash_value.py
The hash for 1 is: 1
The hash for 1.0 is: 1
The hash for 3.14 is: 322818021289917443
The hash for Python is: -4091130140068130420
The hash for a tuple of vowels is: -4853987341791766651
The hash for an object of person is: -4495813431635817990
PS C:\Users\mrdan\iot\lesson10> python hash_value.py
The hash for 1 is: 1
The hash for 1.0 is: 1
The hash for 3.14 is: 322818021289917443
The hash for Python is: -8652938607949081249
The hash for a tuple of vowels is: -7084159014097113383
The hash for an object of person is: -2882680852001230752
```
```
PS C:\Users\mrdan\iot\lesson10> python
Python 3.13.3 (tags/v3.13.3:6280bb5, Apr  8 2025, 14:47:33) [MSC v.1943 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> import hashlib
>>> m = hashlib.sha256(b"hello, world")
>>> m.hexdigest()
'09ca7e4eaa6e8ae9c7d261167129184883644d07dfba7cbfbc4c8a2e08360d5b'
>>> m.digest_size
32
>>> m.block_size
64
>>> exit()
```
```
PS C:\Users\mrdan\iot\lesson10> cat snakecoin.py
# Gerald Nash, "Let's build the tiniest blockchain in less than 50 lines of Python"
import hashlib as hasher
import datetime as date

# Define what a Snakecoin block is
class Block:
  def __init__(self, index, timestamp, data, previous_hash):
    self.index = index
    self.timestamp = timestamp
    self.data = data
    self.previous_hash = previous_hash
    self.hash = self.hash_block()

  def hash_block(self):
    sha = hasher.sha256()
    sha.update(str(self.index).encode() + str(self.timestamp).encode() + str(self.data).encode() + str(self.previous_hash).encode())
    return sha.hexdigest()

# Generate genesis block
def create_genesis_block():
  # Manually construct a block with
  # index zero and arbitrary previous hash
  return Block(0, date.datetime.now(), "Genesis Block", "0")

# Generate all later blocks in the blockchain
def next_block(last_block):
  this_index = last_block.index + 1
  this_timestamp = date.datetime.now()
  this_data = "Hey! I'm block " + str(this_index)
  this_hash = last_block.hash
  return Block(this_index, this_timestamp, this_data, this_hash)

# Create the blockchain and add the genesis block
blockchain = [create_genesis_block()]
previous_block = blockchain[0]

# How many blocks should we add to the chain
# after the genesis block
num_of_blocks_to_add = 20

# Add blocks to the chain
for i in range(0, num_of_blocks_to_add):
  block_to_add = next_block(previous_block)
  blockchain.append(block_to_add)
  previous_block = block_to_add
  # Tell everyone about it!
  print("Block #{} has been added to the blockchain!".format(block_to_add.index))
  print("Hash: {}\n".format(block_to_add.hash))
PS C:\Users\mrdan\iot\lesson10> python snakecoin.py
Block #1 has been added to the blockchain!
Hash: 0f28702bffa980a4eb838d65a1c7b4cea14a4fb95bcab76f3aa9eaea80593dbc

Block #2 has been added to the blockchain!
Hash: d7c21bf18f28cba1e064f29fbdcfca037001997c07d9d2ff2bff82c82776c463

Block #3 has been added to the blockchain!
Hash: 321606fe33adf8ac3fb3fa19e82f2f288a8bc1ba6f32cc75806be1aa972d043b

Block #4 has been added to the blockchain!
Hash: 83cc6e6881dd78c4e5dd71d9dde4819ab15d5495e0b7c7976daceffc8503de53

Block #5 has been added to the blockchain!
Hash: c3e231ca6a67c7482693ca549528bf9180c125ff826aee1e4abcb32e49a3d759

Block #6 has been added to the blockchain!
Hash: 19a15f440d08bc7113f1fa9e88f02f0c0608753e2fc353e6693ec665f0d30bb1

Block #7 has been added to the blockchain!
Hash: 286d4fc4f025ffa3ce7f6d0fe055f586b61cae7e8ef695d0213223c1e944fc21

Block #8 has been added to the blockchain!
Hash: d06cef04c8b0f7f1cbc4e9e2c5b03108bed48c1910ecc8e5b56bb071f53f4ee0

Block #9 has been added to the blockchain!
Hash: eacb9d747a224102c61b9a4da1668000d99cb17f0436fa6790a6b3c2c7d9ab52

Block #10 has been added to the blockchain!
Hash: 07b133caf67d1a45b9c31ff007a1c9fcf17d26326ff31672929ccddb110174d3

Block #11 has been added to the blockchain!
Hash: 88c471364193f10f4dae0098026e6bf83880e75a47e99fc44a23fc9fb00817e1

Block #12 has been added to the blockchain!
Hash: 5439b09da1fd2564b680ccdd3d08547efebca26a85ea66f7cf1c7d2307ac9c52

Block #13 has been added to the blockchain!
Hash: 2063f3da3603bf71448d3f190a399d93addd21ee11e5238e39ccc4fdf0fa9ce0

Block #14 has been added to the blockchain!
Hash: f8153fee3a057ba8fd22037780f1f6d307f150839d8b8d643aba2c9f17d4c0f5

Block #15 has been added to the blockchain!
Hash: 0951e70ab9e6ac3559a702a977586a4add58c18157b95b0facd0f280a56156b1

Block #16 has been added to the blockchain!
Hash: 475f6ae4658481a44bf2608aa93db831716f826d59911ace117fbe0bdd73dbff

Block #17 has been added to the blockchain!
Hash: 41f50c3119aadbcd96cf2f07b1f6445b87829bcb4b1d2d208d15d77f9b495b61

Block #18 has been added to the blockchain!
Hash: b9d73fb308f74756cb8f639045bc6ddb0a7688ae679a6e93a2f2b75add20b1da

Block #19 has been added to the blockchain!
Hash: 89fa00b2b1662ba2bb070c18036350f83a6d9f64fd5bd40d523217905f2625e6

Block #20 has been added to the blockchain!
Hash: 29b3a247ac88c7bf6bdd83e9739779080de5c0a2a5918f9ff334fc9d0e4ed5d3
```
```
PS C:\Users\mrdan\iot\lesson10> pip install markupsafe==2.0.1 flask
Collecting markupsafe==2.0.1
  Downloading MarkupSafe-2.0.1.tar.gz (18 kB)
  Installing build dependencies ... done
  Getting requirements to build wheel ... done
  Preparing metadata (pyproject.toml) ... done
Requirement already satisfied: flask in c:\users\mrdan\appdata\local\programs\python\python313\lib\site-packages (3.1.0)
Requirement already satisfied: Werkzeug>=3.1 in c:\users\mrdan\appdata\local\programs\python\python313\lib\site-packages (from flask) (3.1.3)
Requirement already satisfied: Jinja2>=3.1.2 in c:\users\mrdan\appdata\local\programs\python\python313\lib\site-packages (from flask) (3.1.6)
Requirement already satisfied: itsdangerous>=2.2 in c:\users\mrdan\appdata\local\programs\python\python313\lib\site-packages (from flask) (2.2.0)
Requirement already satisfied: click>=8.1.3 in c:\users\mrdan\appdata\local\programs\python\python313\lib\site-packages (from flask) (8.1.8)
Requirement already satisfied: blinker>=1.9 in c:\users\mrdan\appdata\local\programs\python\python313\lib\site-packages (from flask) (1.9.0)
Requirement already satisfied: colorama in c:\users\mrdan\appdata\local\programs\python\python313\lib\site-packages (from click>=8.1.3->flask) (0.4.6)
INFO: pip is looking at multiple versions of werkzeug to determine which version is compatible with other requirements. This could take a while.
Collecting Werkzeug>=3.1 (from flask)
  Downloading werkzeug-3.1.2-py3-none-any.whl.metadata (3.7 kB)
  Downloading werkzeug-3.1.1-py3-none-any.whl.metadata (3.7 kB)
  Downloading werkzeug-3.1.0-py3-none-any.whl.metadata (3.7 kB)
Collecting Jinja2>=3.1.2 (from flask)
  Using cached jinja2-3.1.6-py3-none-any.whl.metadata (2.9 kB)
INFO: pip is still looking at multiple versions of werkzeug to determine which version is compatible with other requirements. This could take a while.
  Downloading jinja2-3.1.5-py3-none-any.whl.metadata (2.6 kB)
  Downloading jinja2-3.1.4-py3-none-any.whl.metadata (2.6 kB)
INFO: This is taking longer than usual. You might need to provide the dependency resolver with stricter constraints to reduce runtime. See https://pip.pypa.io/warnings/backtracking for guidance. If you want to abort this run, press Ctrl + C.
  Downloading Jinja2-3.1.3-py3-none-any.whl.metadata (3.3 kB)
  Downloading Jinja2-3.1.2-py3-none-any.whl.metadata (3.5 kB)
Collecting itsdangerous>=2.2 (from flask)
  Using cached itsdangerous-2.2.0-py3-none-any.whl.metadata (1.9 kB)
Collecting click>=8.1.3 (from flask)
  Using cached click-8.1.8-py3-none-any.whl.metadata (2.3 kB)
Collecting blinker>=1.9 (from flask)
  Using cached blinker-1.9.0-py3-none-any.whl.metadata (1.6 kB)
Collecting flask
  Using cached flask-3.1.0-py3-none-any.whl.metadata (2.7 kB)
  Downloading flask-3.0.3-py3-none-any.whl.metadata (3.2 kB)
Collecting Werkzeug>=3.0.0 (from flask)
  Downloading werkzeug-3.0.6-py3-none-any.whl.metadata (3.7 kB)
  Downloading werkzeug-3.0.5-py3-none-any.whl.metadata (3.7 kB)
  Downloading werkzeug-3.0.4-py3-none-any.whl.metadata (3.7 kB)
  Downloading werkzeug-3.0.3-py3-none-any.whl.metadata (3.7 kB)
  Downloading werkzeug-3.0.2-py3-none-any.whl.metadata (4.1 kB)
  Downloading werkzeug-3.0.1-py3-none-any.whl.metadata (4.1 kB)
  Downloading werkzeug-3.0.0-py3-none-any.whl.metadata (4.1 kB)
Collecting flask
  Downloading flask-3.0.2-py3-none-any.whl.metadata (3.6 kB)
  Downloading flask-3.0.1-py3-none-any.whl.metadata (3.6 kB)
  Downloading flask-3.0.0-py3-none-any.whl.metadata (3.6 kB)
  Downloading flask-2.3.3-py3-none-any.whl.metadata (3.6 kB)
Collecting Werkzeug>=2.3.7 (from flask)
  Downloading werkzeug-2.3.8-py3-none-any.whl.metadata (4.1 kB)
  Downloading werkzeug-2.3.7-py3-none-any.whl.metadata (4.1 kB)
Collecting flask
  Downloading Flask-2.3.2-py3-none-any.whl.metadata (3.7 kB)
Collecting Werkzeug>=2.3.3 (from flask)
  Downloading Werkzeug-2.3.6-py3-none-any.whl.metadata (4.1 kB)
  Downloading Werkzeug-2.3.5-py3-none-any.whl.metadata (4.1 kB)
  Downloading Werkzeug-2.3.4-py3-none-any.whl.metadata (4.2 kB)
  Downloading Werkzeug-2.3.3-py3-none-any.whl.metadata (4.2 kB)
Collecting flask
  Downloading Flask-2.3.1-py3-none-any.whl.metadata (3.7 kB)
Collecting Werkzeug>=2.3.0 (from flask)
  Downloading Werkzeug-2.3.2-py3-none-any.whl.metadata (4.2 kB)
  Downloading Werkzeug-2.3.1-py3-none-any.whl.metadata (4.2 kB)
  Downloading Werkzeug-2.3.0-py3-none-any.whl.metadata (4.2 kB)
Collecting flask
  Downloading Flask-2.3.0-py3-none-any.whl.metadata (3.7 kB)
  Downloading Flask-2.2.5-py3-none-any.whl.metadata (3.9 kB)
Collecting Werkzeug>=2.2.2 (from flask)
  Downloading Werkzeug-2.2.3-py3-none-any.whl.metadata (4.4 kB)
  Downloading Werkzeug-2.2.2-py3-none-any.whl.metadata (4.4 kB)
Collecting Jinja2>=3.0 (from flask)
  Downloading Jinja2-3.1.1-py3-none-any.whl.metadata (3.5 kB)
  Downloading Jinja2-3.1.0-py3-none-any.whl.metadata (3.5 kB)
  Downloading Jinja2-3.0.3-py3-none-any.whl.metadata (3.5 kB)
  Downloading Jinja2-3.0.2-py3-none-any.whl.metadata (3.5 kB)
  Downloading Jinja2-3.0.1-py3-none-any.whl.metadata (3.5 kB)
  Downloading Jinja2-3.0.0-py3-none-any.whl.metadata (3.5 kB)
Collecting flask
  Downloading Flask-2.2.4-py3-none-any.whl.metadata (3.9 kB)
  Downloading Flask-2.2.3-py3-none-any.whl.metadata (3.9 kB)
  Downloading Flask-2.2.2-py3-none-any.whl.metadata (3.9 kB)
  Downloading Flask-2.2.1-py3-none-any.whl.metadata (3.9 kB)
Collecting Werkzeug>=2.2.0 (from flask)
  Downloading Werkzeug-2.2.1-py3-none-any.whl.metadata (4.4 kB)
  Downloading Werkzeug-2.2.0-py3-none-any.whl.metadata (4.4 kB)
Collecting flask
  Downloading Flask-2.2.0-py3-none-any.whl.metadata (3.9 kB)
  Downloading Flask-2.1.3-py3-none-any.whl.metadata (3.9 kB)
Collecting Werkzeug>=2.0 (from flask)
  Downloading Werkzeug-2.1.2-py3-none-any.whl.metadata (4.4 kB)
Downloading Flask-2.1.3-py3-none-any.whl (95 kB)
Downloading Werkzeug-2.1.2-py3-none-any.whl (224 kB)
Building wheels for collected packages: markupsafe
  Building wheel for markupsafe (pyproject.toml) ... done
  Created wheel for markupsafe: filename=markupsafe-2.0.1-py3-none-any.whl size=9800 sha256=d79dc59ac2d4cf8e6523dff786468ed16aa6a66bc3934531c08da9a0a17434be
  Stored in directory: c:\users\mrdan\appdata\local\pip\cache\wheels\da\8d\58\218e689fb21a07c5e22ee25602c0574884c907825f578eafea
Successfully built markupsafe
Installing collected packages: Werkzeug, markupsafe, flask
  Attempting uninstall: Werkzeug
    Found existing installation: Werkzeug 3.1.3
    Uninstalling Werkzeug-3.1.3:
      Successfully uninstalled Werkzeug-3.1.3
  Attempting uninstall: markupsafe
    Found existing installation: MarkupSafe 3.0.2
    Uninstalling MarkupSafe-3.0.2:
      Successfully uninstalled MarkupSafe-3.0.2
  Attempting uninstall: flask
    Found existing installation: Flask 3.1.0
    Uninstalling Flask-3.1.0:
      Successfully uninstalled Flask-3.1.0
Successfully installed Werkzeug-2.1.2 flask-2.1.3 markupsafe-2.0.1
```

---
<h4 id="100">Postscript</h4>

- All my source files were initially obtained in [`Dr. Lu's GitHub`](https://github.com/kevinwlu/iot/tree/master/lesson10)
- Please note, I replaced all the instances of "python3" with "python" in the commands for the lab, as I had Python downloaded on my system already.
- I pledge my honor that I have abided by the Stevens Honor System: Daniel A. Liss
