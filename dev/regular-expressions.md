# Regular Expressions

## Used Expressions

### New Line

matches any Unicode newline sequence; can be modified using verbs

```php
$string = preg_replace('/\R/u', '[,nL]', $string); // Probleme mit Umlauten
$string = preg_replace("/\r|\n/s", '[,nL]', $string);
```

## Tools

- [grex](https://github.com/pemistahl/grex)

## Links

- [regex101](https://regex101.com/) for testing
- [iHateRegex](https://ihateregex.io/)
- [Learn Regex the easy way](https://github.com/ziishaned/learn-regex/blob/master/translations/README-de.md)