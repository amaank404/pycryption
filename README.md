# Pycryption
A simple library to encrypt text or bytes with only 2 simple functions, `encrypt` and `decrypt`

## Installation

Using pip
```
pip install pycryption -U
```

## Usage

Here is a simple example to understand all that this library can do

```python
>>> import pycryption
>>> sample_text = "abcdefghij"
>>> password = "my_password"
>>> encrypted = pycryption.encrypt(sample_text, password)  # Encrypt Data (can also take bytes)
>>> print(encrypted)
b'16;32;48/>\x15Y^\xa3\xc66v\x83\x9d\xfc\x19;p\xf2\x88\xbe3\xaao\x18_\x91\xe4\xbb0\x98\xdba\x06Q\x10\x15\x15\xe0\xcb\x14\x8bw\xa0\xef\x875j<\x1d\x06H\x04\xf6\x13\x01&\xa7\x12\x80}\x18'
>>>
>>> pycryption.decrypt(encrypted, "Wrong_Password")
Traceback (most recent call last):
  ...
ValueError: MAC check failed
>>> pycryption.decrypt(encrypted, password)  # Always returns bytes
b'abcdefghij'
```
