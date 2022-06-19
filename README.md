![LightView](./docs/header.png)

# LightView

A Fast, Easy and Lightweight Template Engine for Web Applications. [Based on article by David Adams](https://codeshack.io/lightweight-template-engine-php/). The unique feature added is concept of computed output.
## Features

    * Fast
    * Easy
    * Lightweight
    * Supports Layout
    * Supports Computed output


## Installtion
```
composer require nabeelalihashmi/LightView
```

## Basic Usage

Configure your application's views folder and cache folder

```
LightView::$cache_path = '../cache';
LightView::$views_path = '../app/views';
```

Render the view like

```
LightView::render('myView.html', ['message' => 'Hi']);
```

A view can be:
```
<!-- layout.html -->
<!DOCTYPE html>
<html>
	<head>
		<title>{% yield title %}</title>
        <meta charset="utf-8">
	</head>
	<body>
	{% include partials/nav.html %}
    {% yield content %}
    </body>
</html>

<!-- myView.html -->
{% extends layouts/main.html %}

{% block title %}Home Page{% endblock %}

{% block content %}
<h1>Home</h1>
<p>Welcome to the home page!</p>
<p>
    We Have A Message For You
    {{ $message }}
    {% 
        echo 'hi';   
    %}
    
</p>
{% endblock %}

```

## Layout
Layout can be simple file having multiple yields and includes.


## PHP Code
You can use php code inside `{% %}` block

```
{%  echo 'hi'; %}
{%  foreach($messages as $message): %}
<li> {{ $msg }} </li>
{% endforeach %}    
```
-------------------------

## Computed Block

This outputs the html output of code instead of echoing. Good for saving resources.
```
{( Namespace\Class,method,arg1,arg2 )}
```
## Print Escaped 

```
{{ $variable }}
```

## Print Unescape 

```
{! $variable !}
```
## License

LightView is released under permissive licese with following conditions:

* It cannot be used to create adult apps.
* It cannot be used to gambling apps.
* It cannot be used to create apps having hate speech.

### MIT License

Copyright 2022 Nabeel Ali | IconicCodes.com

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

