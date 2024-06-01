```
<?php
    $n = (int)trim(fgets(STDIN));
    
    $price_list = array_map('intval', explode(' ', trim(fgets(STDIN))));
    
    $new_price_list = [];
    foreach ($price_list as $key => $pl)
    {
        $new_price_list[$key+1] = $pl;
    }
    
     list($my_money, $m)= array_map('intval', explode(' ', trim(fgets(STDIN))));
     
     for($i=0;$i<$m;$i++)
     {
         list($item_num, $buy_num)= array_map('intval', explode(' ', trim(fgets(STDIN))));
         
         if($my_money - $new_price_list[$item_num]*$buy_num >= 0)
         {
             $my_money -= $new_price_list[$item_num]*$buy_num;
         }
     }
     
     print_r($my_money);
?>
```
