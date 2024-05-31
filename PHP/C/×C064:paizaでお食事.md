1つのテストケースだけ失敗する

```
<?php
list($item_num, $person_num) = array_map('intval', explode(' ', trim(fgets(STDIN))));

$calorie = [];
for ($i = 0; $i < $item_num; $i++) {
    $calorie[] = (int)trim(fgets(STDIN));
}

$person_data = [];
for ($j = 0; $j < $person_num; $j++) {
    $person_data[] = array_map('intval', explode(' ', trim(fgets(STDIN))));
}

for ($k = 0; $k < $person_num; $k++) {
    $total_calories = 0;
    $target = $person_data[$k];
    
    for ($l = 0; $l < $item_num; $l++) {
        $total_calories += round($calorie[$l] * ($target[$l] / 100));
    }
    
    echo $total_calories . "\n";
}
?>
```
