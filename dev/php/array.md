# Array

## Sortieren

### Nach Wert

```php
usort($myArray, function($a, $b) {
    return $a['order'] <=> $b['order'];
});
```

### Nach mehreren Werten

```php
foreach ($data as $key => $row) {
    $value_1[$key] = $row['value_1'];
    $value_2[$key] = $row['value_2'];
}

array_multisort($value_1, SORT_ASC, $value_2, SORT_ASC, $data);
```

oder

```php
array_multisort(array_column($data, 'value_1'), SORT_ASC, array_column($data, 'value_2'), SORT_ASC, $data);
```

