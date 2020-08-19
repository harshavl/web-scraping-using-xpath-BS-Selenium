
# Two ways using lxml:
1. css selectors;
2. xpath


## CSS selectors:
- module: cssselect
replace find -> cssselect


Using Cssselectors:
[css] https://try.jsoup.org/


CSS query:
select header 1:
> h1

list all intro class 
> .intro 

How to select indivisual intro class ? using span id;
>  #location 
> span#location  or #location

How classify two classes?
> .bold
> .bold.italic

we have class,id, div, and data identifier and href;

How to select data identifier ?
> li

> li[data-identifier]

> li[data-identifier=7]

> [data-identifier=7]

How to use conditions in  cssselect ?

select starts with https?

> a[href]

> a[href]^='https']

select ends with 'fr' ?

> a[href $='fr']

Select in the middle strings ?

a[href *='google']

How to select based on the positions ?

> div.intro p ( not selected the last p or after div paragraph )

> div.intro p, span#location

> div.intro p, #location

> div.intro > p ( same above )

> div.intro + p ( places after div )

> div.intro + span ( this wont work due to select only after div )

How to select elements based on positions ? n-thchild

select list of li?

> li

select 1st item ?

> li:nth-child(1)

select 1 and 3 ?

> li:nth-child(1), li:nth-child(3)

select even and odd ?

> li:nth-child(even)
> li:nth-child(odd)

select between div and ( some other elements ) p ?

> div ~ p


# Using xpath

select header?

> //h1

select div and class intro ?

> //div
> //div[@class='intro']

if inside the element? use paragraph

> //div[@class='intro']/p

select both classes intro and outer ?

> //div[@class='intro' or @class='outer']/p

convert to text ?

> //div[@class='intro' or @class='outer']/p/text()

Select href attributes ?
> //a

select href starts with https ?
> //a[starts-with()]
> //a[ starts-with( @href , 'https' ) ]
> //a[ ends-with( @href , 'fr' ) ]
> //a[  contains( @href , 'fr' ) ]
> //a[  contains( @href , 'google' ) ]

Search in the text ?

> //a[  contains(  text() , 'France' ) ]

Hw to select elements based on positions ?

> //ul
> //ul[ @id = 'items']/li
> //ul[ @id = 'items']/li[1]
> //ul[ @id = 'items']/li[1 or 4]

> Another method using position :
> //ul[ @id = 'items']/li[ position() = 1 ]

select 1 and 4:

> //ul[ @id = 'items']/li[ position() = 1  or position() = 4 ]

In case, we don't what is the last position ?
> //ul[ @id = 'items']/li[ position() = 1  or position() = last() ]
> //ul[ @id = 'items']/li[ position() >1  or position() = last() ] 

Navigating using Xpath( Going UP ):

> //div[ @class='intro']/p

print the parents?

select the parent of the outside elements?
> //p[ @id='outside']/parent::node()

Print all the parents of the elements ?
> //p[ @id='outside']/ancestor::node()

Print ancestor and self ?
> //p[ @id='outside']/ancestor-or-self::node()

Print preceding from parent or printing from begining  ?
> //p[ @id='outside']/preceding::node()

print header from preceding?
> //p[ @id='outside']/preceding::h1

> //p[ @id='outside']/preceding::body ( not works )

print sibling of the element or Just above the elements ?
> //p[ @id='outside']/preceding-sibling::node()

Navigating Going Down;

Print down after Element;
> //div[ @class='intro' ]/p

> //div[ @class='intro' ]/child::p

> //div[ @class='intro' ]/child::node()

Print all element after the id?
> //div[ @class='intro' ]/following::node()

Print body element of the same parent?
//div[ @class='intro' ]/following-sibling::node()

Print Child children or grand children;
> //div[ @class='intro' ]/descendant::node()


How the web works ?
- Client and server;
- both uses HTTP protocol;
- HTTP verbs: GET POST PATCH;

