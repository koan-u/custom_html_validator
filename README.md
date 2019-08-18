# Custom_HTML_Validator for Python

custom_html_validator is python library , it can validate HTML tags and attrs.
It is created using HTMLParser, a standard python module, and the basic usage is the same.  
As a change from the original, this module can check if the text contains anything other than arbitrary HTML tags and attrs.  

## Installation
```
pip install custom_html_validator
```

## Examples
### import
```
from custom_html_validator import CustomHTMLValidater
```

### initialization
```
    # This is any HTML tag and attribute that you allow
    ALLOWED_TAGS = {
        # 'tag': ['attr1','attr2']
        'a':['href',''],
        'br':[]
    }
    
    parser = CustomHTMLValidater()
    parser.set_allowed_tags(ALLOWED_TAGS)
    
```

### validation
```
    parser.feed(target_str)
    results = parser.close()
    
    # validate result is 1(ok) or -1(NG)
    if results['status'] == 1:
        # validate OK
    elif results['status'] == -1:
        # validate NG
        # results['detail'] is a sentence describing the error
```

### Clear result
If you want validate another sentence , you have to reset parser
```
    # This does not reset the allowed tags
    parser.reset()

    # You could use this, if you want to reset allowed tags
    parser.reset(True)
```

## License
**MIT LICENSE**
