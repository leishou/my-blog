# VS-del .vs js

```
const fs = require('fs');  
const path = require('path');  
  
function deleteVSFolder(dirPath) {  
  const files = fs.readdirSync(dirPath);  
  
  for (const file of files) {  
    const filePath = path.join(dirPath, file);  
    const stat = fs.statSync(filePath);  
  
    if (stat.isDirectory()) {  
      // 判断文件夹是否为隐藏文件夹  
      if (file === '.vs' && file.startsWith('.')) {  
        fs.rmdirSync(filePath, { recursive: true });  
        console.log(`Deleted folder: ${filePath}`);  
      } else {  
        deleteVSFolder(filePath);  
      }  
    }  
  }  
}  
  
const currentPath = process.cwd();  
deleteVSFolder(currentPath);  
```

