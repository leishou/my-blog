# 工具js

按行获取键值和要替换的value(嵌套key值在单行列出) 调好js了 可行解

```
<!DOCTYPE html>
<html>
  <head>
    <title>JSON Value Replacement</title>
    <script>
      function findValue(obj, key) {
        var value = obj[key];
        if (typeof value === 'object') {
          return JSON.stringify(value);
        }
        return value;
      }

      function setValue(obj, key, newValue) {
        var keyPath = key.split(' ');
        if (keyPath[0].trim() === key) {
          obj[key] = newValue;
          return true;
        } else {
          var nestedKey = keyPath.slice(1).join('').trim();
          if (obj.hasOwnProperty(keyPath[0].trim())) {
            return setValue(obj[keyPath[0].trim()], nestedKey, newValue);
          } else {
            for (var prop in obj) {
              if (typeof obj[prop] === 'object' && setValue(obj[prop], key, newValue)) {
                return true;
              }
            }
          }
        }
        return false;
      }

      function replaceNestedJSONValues() {
        var inputText = document.getElementById('inputText').value;
        var keys = document.getElementById('keys').value.split('\n');
        var json = {
          '1': 'value1',
          '2': 'value2',
          '3': {
            '7': 'value3',
          },
          '5': {
            '6': { '7': 'value4' },
          },
        };

        keys.forEach(function (keyValue, index) {
          var keyPath = keyValue.split(':');
          var key = keyPath[0].trim();
          var newValue = inputText.split('\n')[index].trim();

          setValue(json, key, newValue);
        });

        console.log(json);
      }
    </script>
  </head>
  <body>
    <textarea id="inputText" rows="20" cols="50"></textarea><br />
    <textarea type="text" id="keys" rows="20" cols="50"></textarea><br />
    <button onclick="replaceNestedJSONValues()">Replace Values</button>
  </body>
</html>
```

