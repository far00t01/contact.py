
# form1
This Python script analyzes the source code to identify contact forms within the HTML code. It allows you to perform analyses with a single URL or a file containing multiple URLs. This script was primarily created to identify the possibility of the "[HyperLink Injection](https://medium.com/@far00t01/hyperlink-injection-an-underrated-vulnerability-29e93bbd967b)" vulnerability in the contact forms of an application.


<div style="text-align: center;">
  <img src="https://github.com/far00t01/form1/blob/main/form1-banner.png" alt="Formulario con lupa" width="1400"/>
</div>

## Features

- **Contact Form Search**: Analyzes the HTML code of a given URL or a set of URLs from a file to find links related to "contact".
- **Form Verification**: Verifies that the found pages contain forms with fields like "name" and "email".
- **Results**: Displays the results in the console and saves them in a file called `result.txt`.


## Usage:
```
python3 form1.py

usage: form1.py [-h] [-u URL] [-f FILE] [-d]

Find contact forms in a website.

options:
  -h, --help            show this help message and exit
  -u URL, --url URL     URL of the website to scan
  -f FILE, --file FILE  File containing list of URLs to scan
  -d, --debug           Enable debug mode
```

### Scan a Single URL
```
python3 form1.py -u example.com

Found contact forms:
- https://www.example.com/contact
```

### Scan a Single URL with debug method 
```
python3 form1.py -u example.com -d 

Checking URL: https://example.com
Successfully retrieved https://example.com
Found potential contact URL: https://example.com/contacto/
Checking form at URL: https://example.com/contacto/
Successfully retrieved form page at https://example.com/contacto/
Form found with inputs: ['s']
Form found with inputs: ['s']
Form found with inputs: ['nombre', 'apellidos', 'email', 'telefono', 'direccion', '', '_wpcf7_ak_js']
Form with required input fields found at https://example.com/contacto/

Found contact form:
- https://example.com/contacto/
```

### Scan Multiple URLs from a File
```
python3 form1.py -f urls.txt

Found contact forms:
 - https://www.example.com/contact
 - https://www.support.example.com/pages/contact
 - https://www.portal.example.com/contact-us
 - https://www.other.com/
```

### Output
```
Content of result.txt:

Found contact form: https://www.example.com/contact
Found contact form: https://www.support.example.com/pages/contact
Found contact form: https://www.portal.example.com/contact-us
Found contact form: https://www.other.com/
```

# Installation Requirements

### System Requirements
- **Python**: Make sure you have Python 3.x installed. You can check this by running `python3 --version` in your terminal.

### Install

```
git clone https://github.com/far00t01/form1.git
cd form1 
pip install -r requirement.txt
python3 form1.py
```

