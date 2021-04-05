# Serialize

Daten aus PHP in Datenbank oder Datei speichern

```
$array = [
    0 => 1,
    'foo' => 'bar',
];
$serialized = serialize($array);
echo $serialized;
```

Ergebnis:
```
a:2:{i:0;i:1;s:3:"foo";s:3:"bar";}
```

- a: Array
- i: Integer
- s: String
- Zahl: Länge

## serialize

```
$serialized = serialize($array);
```

## unserialize

```
$array = unserialize($serialized);
```

### fix

Neu berechnen der Länge der Variablen:

```
function unserializeAndFix(string $serialized) : array
{
    $unserialized = unserialize($serialized);
    if ($unserialized !== false) {
        return $unserialized;
    }

    return unserialize(fixSerializedString($serialized));
}

function fixSerializedString(string $serialized) : string
{
    return preg_replace_callback(
        '/s:([0-9]+):\"(.*?)\";/',
        function ($matches) {
            return "s:".strlen($matches[2]).':"'.$matches[2].'";';
        },
        $serialized
    );
}

$filename = './serialized.txt';
$serialized = file_get_contents($filename);
$unserialized = @unserialize($serialized);
if ($unserialized !== false) {
    echo 'Keine Fehler gefunden.' . PHP_EOL;
    exit;
}
$fixed = fixSerializedString($serialized);

$unserialized = @unserialize($fixed);
if ($unserialized === false) {
    echo 'Fehler konnten nicht repariert werden.' . PHP_EOL;
    exit;
}
file_put_contents($filename, "\n\nFixed:\n" . $fixed, FILE_APPEND);

echo 'Fehler gefunden und repariert.' . PHP_EOL . 'Ergebnis in ' . $filename . ' gespeichert.' . PHP_EOL;
```