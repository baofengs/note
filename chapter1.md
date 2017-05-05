# gulp

## 安装

```
npm install -g gulp
```

## 基本使用

```
// 文件拷贝
var gulp = require('gulp');

gulp.task('cp', function() {
    gulp.src('index.html')
        .pipe('..');
})

gulp.task('default', ['cp']);
```

## 结合相关 gulp 插件使用

### 插件获取: \[npmjs\]\(https://www.npmjs.com/\)





