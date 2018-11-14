---
weight: 2
title: Autenticazione
---


# Autenticazione


> Per effettuare il login, questo è il codice:

```python
package main

import "github.com/bep/kittn/auth"

func main() {
	api := auth.Authorize("meowmeowmeow")

	// Just to make it compile
	_ = api
}

```

> Risposta

```python
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}

```

```php
$login
```

Per autenticarsi con donodoo sono necessarie le seguenti informazioni

- Nome del database
- Nome utente
- Password
