# gulp

> * gulp 安装 & 基本使用
> * gulp 插件安装 & 使用
>   * gulp-sass
>   * browser-sync
>   * gulp-autoprefixer
>   * gulp-minify-css
>   * gulp-imagemin & imagemin-pngquant

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

## 结合相关 gulp 插件使用\([npmjs](https://www.npmjs.com/)\)

### browser-sync：浏览器同步更新

#### 安装

```
npm install --save-dev browser-sync
```

#### 使用

```
// 设置上一级目录为访问根目录
var browserSync = require('browser-sync').create;

gulp.task('server', function() {
    browserSync.init({
        server: {
            baseDir: '..'
        }
    })
})

gulp.task('default', ['server'])
```

### gulp-sass：编译 sass

#### 安装

```
npm install --save-dev gulp-sass
```

#### 使用

```
var sass = require('gulp-sass');

gulp.task('sass', function() {
    gulp.src('styles/*.scss')
        .pipe(sass())
        .pipe(gulp.dest('../styles'));
})
```

### gulp-autoprefixer：自动添加厂商前缀

#### 安装

```
npm install --save-dev gulp-autoprefixer
```

#### 使用

```
var sass = require('gulp-sass');
var prefix = require('gulp-autoprefixer');

gulp.task('sass', function() {
    gulp.src('styles/*.scss')
        .pipe(sass())
        .pipe(prefix())
        .pipe(gulp.dest('../styles'));
})
```

### gulp-minify-css：css 压缩

### gulp-imagemin & imagemin-pngquant：图片压缩

#### 安装

```
npm install --save-dev gulp-imagemin imagemin-pngquant
```

#### 使用

```
var imgmin = require('gulp-imagemin');
var pngquant= require('imagemin-pngquant');

gulp.task('imagemin', function() {
    return gulp.src('src/imges/*')
        .pipe(imgmin({
            progressive: true,
            svgPlugins: [{removeViewBox: false}],
            use: [pngquant()]
        }))
        .pipe(gulp.dest('dist/images'));
})
...
```



