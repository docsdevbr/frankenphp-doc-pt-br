<!--
[//]: # Copyright (c) 2022-present Kévin Dunglas.

[//]: # Documentation licensed under the MIT License.
[//]: # The original work was translated from English into Brazilian Portuguese.
[//]: # https://github.com/php/frankenphp/blob/main/LICENSE

source_url: https://github.com/php/frankenphp/blob/main/docs/early-hints.md
revision: dd6b33a35cc4a2a20f9dc6b5ba43475cad81af17
status: review
-->

# Early Hints

O FrankenPHP suporta nativamente o
[código de status 103 Early Hints](https://developer.chrome.com/blog/early-hints/).
Usar Early Hints pode melhorar o tempo de carregamento das suas páginas web em
30%.

```php
<?php

header('Link: </style.css>; rel=preload; as=style');
headers_send(103);

// seus algoritmos e consultas SQL lentos 🤪

echo <<<'HTML'
<!DOCTYPE html>
<title>Olá FrankenPHP</title>
<link rel="stylesheet" href="style.css">
HTML;
```

As Early Hints são suportadas tanto pelo modo normal quanto pelo modo
[worker](worker.md).
