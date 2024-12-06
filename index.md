<!DOCTYPE html>
<html lang="uk">
<head>
    <title>Cтворення HTML-презентацій з Remark</title>
    <meta charset="utf-8">
    <link rel="icon" type="image/svg+xml" href="https://image.flaticon.com/icons/svg/957/957493.svg" />
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.12.1/css/all.min.css" />
    <style>
        @import url(https://fonts.googleapis.com/css?family=Yanone+Kaffeesatz);
        @import url(https://fonts.googleapis.com/css?family=Droid+Serif:400,700,400italic);
        @import url(https://fonts.googleapis.com/css?family=Ubuntu+Mono:400,700,400italic);

        body { font-family: 'Droid Serif'; }
        h1, h2, h3 {
            font-family: 'Yanone Kaffeesatz';
            font-weight: normal;
        }
        .remark-code, .remark-inline-code { font-family: 'Ubuntu Mono'; }
    </style>
</head>
<body>
    <textarea id="source">

class: center, middle

# Титульний слайд

---

# Зміст

--

1. Вступ

--

2. Основна частина

--

3. Закінчення

---

# Вступ

Деякий текст.

---

# Основна частина

Розділ 1.

--

- Підрозділ 1.1

--

- Підрозділ 1.2

--

Розділ 2.

--

- Підрозділ 2.1

---

# Закінчення

Деякий текст.

    </textarea>
    <script src="https://remarkjs.com/downloads/remark-latest.min.js"></script>
    <script>    
        var slideshow = remark.create();
    </script>
</body>
</html>
