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

    // array_map(関数, 配列)の形で使う。このとき、第二引数の配列の要素を一つずつ取得して、第一引数の関数を実行さ背ていく。

    $new_target = array_map(function($n) use ($list) {
       return $list[$n] ?? $n;
    }, $new_target);
    
    print_r(implode($new_target));
?>
```
