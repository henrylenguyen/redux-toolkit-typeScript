# Hướng dẫn khởi tạo dự án typeScript

  ### Bước 1: Cài đặt dự án bằng yarn (sử dụng yarn nhanh)

```
  yarn create react-app redux --template typescript
```

### Bước 2: Cài đặt các config

```
  yarn add -D prettier eslint-plugin-prettier eslint-config-prettier
```

### Bước 3: Cấu hình eslint

- Mở **package.json** tại phần **"script"** thêm:

```
    "lint": "eslint --ext ts,tsx src/",
    "lint:fix": "eslint --fix --ext ts,tsx src/",
    "prettier": "prettier --check \"src/**/(*/.tsx|*.ts|*.css|*.scss)\"",
    "prettier:fix": "prettier --write \"src/**/(*/.tsx|*.ts|*.css|*.scss)\""

```

=> Đây là cú pháp check và sửa lỗi của eslint và prettier

### Bước 4: Tạo file .prettierrc ngoài global dự án và cấu hình như dưới

```
 {
 "arrowParens": "always",
 "semi": false,
 "trailingComma": "none",
 "tabWidth": 2,
 "endOfLine": "auto",
 "useTabs": false,
 "singleQuote": true,
 "printWidth": 120,
 "jsxSingleQuote": true
}

```

### Bước 5: Tạo file .eslintrc ngoài global dự án và cấu hình như dưới:

```
{
 "extends": ["react-app","prettier"],
 "plugins": ["react","prettier"],
 "rules": {
   "prettier/prettier":[
     "warn",
     {
       "arrowParens": "always",
       "semi": false,
       "trailingComma": "none",
       "tabWidth": 2,
       "endOfLine": "auto",
       "useTabs": false,
       "singleQuote": true,
       "printWidth": 120,
       "jsxSingleQuote": true
     }
   ]
 }
}
```

### Bước 6: Tạo file .editorconfig để cấu hình IDE

```
[*]
index_size = 2
indent_style = space

```

### Bước 7: Mở file tsconfig.json thêm cấu hình dưới để thuận tiện cho việc import

```
"baseUrl": "src"
```
# Check các lỗi bằng lint và prettier

### Tìm kiếm các lỗi
```
yarn lint
```
### Fix nhanh các lỗi

```
yarn lint:fix
```
# Cài đặt các thư viện cần thiết

## Tailwindcss

```
yarn add -D tailwindcss postcss autoprefixer
yarn tailwindcss init

```

## Cấu hình tailwindcss

### Bước 1: vào tailwind.config.js thêm đoạn dưới

```
content: ['./src/**/*.{js,jsx,ts,tsx}'],

```

### Bước 2: Cài thư viện sass vào để có thể biến file .css thành .scss

```
yarn add sass node-sass

```
### Bước 3: đổi đuôi index.css thành index.scss và import code dưới:


```
@tailwind base;
@tailwind components;
@tailwind utilities;

```
## Config prettier tailwindcss

```
yarn add -D prettier-plugin-tailwindcss
```

## Redux toolkit

```
yarn add @reduxjs/toolkit react-redux

```