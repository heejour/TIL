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


### resource
https://stackoverflow.com/questions/590163/how-to-get-all-options-of-a-select-using-jquery