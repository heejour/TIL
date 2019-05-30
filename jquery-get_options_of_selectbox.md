# jquery - How to get all options of a select using jquery

$.map 을 사용해서 가져올 수 있다.

```javascript
/* id를 이용하는 경우 */

var options = $('#selectBox option');

var values = $.map(options ,function(option) {
    return option.value;
});

```
```javascript
/* name을 이용하는 경우 */

var options = $('select[name=selectBox] option');

var values = $.map(options ,function(option) {
    return option.value;
});

```
<br>

- 특정 순서의 값을 가져와보자
```javascript
/* 첫번째 */
$("#selectBox").val($("#selectBox option:first").val());
```

```javascript
/* 두번째 */
$("#selectBox").val($("#selectBox option:eq(1)").val());
```

### resource
- https://stackoverflow.com/questions/590163/how-to-get-all-options-of-a-select-using-jquery
- https://stackoverflow.com/questions/6713143/select-optionsecond-val-jquery-keep-select-second-value-of-select-box