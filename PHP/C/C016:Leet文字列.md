解答1
```
<?php
    // 自分の得意な言語で
    // Let's チャレンジ！！
    $target = trim(fgets(STDIN));
    
    $new_target = str_split($target);
     
    $list = array(
       "A" => 4,
       "E" => 3,
       "G" => 6,
       "I" => 1,
       "O" => 0,
       "S" => 5,
       "Z"=> 2
    );
    
    foreach($new_target as &$n)
    {
        foreach($list as $key => &$value)
        {
            if ($n === $key)
            {
                $n = $value;
            }
        }
    }
    
    print_r(implode($new_target));
?>
```

解答2
```
<?php
    // 自分の得意な言語で
    // Let's チャレンジ！！
    $target = trim(fgets(STDIN));
    
    $new_target = str_split($target);
     
    $list = array(
       "A" => 4,
       "E" => 3,
       "G" => 6,
       "I" => 1,
       "O" => 0,
       "S" => 5,
       "Z"=> 2
    );
    
    $new_target = array_map(function($n) use ($list) {
       return $list[$n] ?? $n;
    }, $new_target);
    
    print_r(implode($new_target));
?>
```
