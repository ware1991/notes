#把get/user-timeline的method在GetTwitterAPI.php實作
GetTwitterAPI.php
---











#註：
這樣輸出的格式是array，所以相對應的來源資料應該要是array

輸出：
```
@foreach ($twits as $person) <li>{{ $person['text'] }}</li>@endforeach
```
來源資料：
```
$twits = Twitter::getUserTimeline(['screen_name' => 'AShinOfficial', 'format' => 'array']);
```

如果來源資料是object，輸出格式相對就要是object

輸出：
```
@foreach ($twits as $person)
    <li> {{ $person->text }} </li>
@endforeach
```
來源資料（format預設是object）
```
$twits = Twitter::getUserTimeLine(['screen_name' =>'AShinOfficial');
```


