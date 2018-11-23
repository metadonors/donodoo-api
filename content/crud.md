---
weight: 10
title: CRUDL
---

# CRUD

## Creazione

> Creazione di un oggetto

```python

vals = {
    'firstname': 'Mario',
    'lastname': 'Rossi',
    'email': 'mario@rossi.it'
}

odoo.env['ngo.donor'].create(vals)

```

```php
$vals = [
    'firstname' => 'Mario',
    'lastname' => 'Rossi',
    'email' => 'mario@rossi.it'
]

$odoo->env['ngo.donor']->create(vals)

```

> Risposta 

```python
12345 # Id della risorsa creata
```

```php
12345 # Id della risorsa creata
```

Per creare un oggetto si utilizza il metodo _create_ legato a tutte le risorse Donodoo. Come parametro un dizionario con i valori dell'oggetto da creare.

### create(values)

* **values:** dizionario di valori con cui inizializzare l'oggetto


## Lettura

> Lettura di uno o piu' oggetti

```python

donor_id = odoo.env['ngo.donor'].browse(12345)

print(donor_id.name)

donor_ids = odoo.env['ngo.donor'].browse([12345, 12346, 12347])

for donor_id in donor_ids:
    print(donor_id.name)

```

```php

$donor_id = $odoo->env['ngo.donor']->browse(12345);

echo "{$donor_id->name}\n";

$donor_ids = $odoo->env['ngo.donor']->browse([12345, 12346, 12347]);

foreach($donor_ids as $donor_id) {
    echo "{$donor_id->name}\n";
}

```

Per leggere i dati relativi ad un oggetto (o a piu' oggetti) partendo dai loro _id_ e' possibile usare il metodo _browse_

### browse(id|ids)

* **id|ids:** puo' essere un intero rappresentante un _id_ di un oggetto, opppure una lista di interi per leggere piu' oggetti in una sola chiamata

## Ricerca

> Ricerca di oggetti

```python

ids = odoo.env['ngo.donor'].search([
    ('email', 'like','gmail.com')
])

print(ids)

```

```php
$ids = $odoo->env['ngo.donor']->search([
    ['email','like','gmail.com']
])

print_r(ids)

```

> Risposta

```
# lista di _id_ relativi alla ricerca
[
    12345,
    12346,
    12347
]
```


E' possibile effettuare ricerche su un determato insieme di oggetti per farlo si ricorre al metodo _search_

### search(domain, limit, offset)

* **domain:** esprime il dominio della ricerca, e' una lista di tuple composte da _campo_,_operatore_,_valore_
* **limit:** il numero massimo di elementi da restituire nella ricerca
* **offset:** l'offset da cui partire nei risultati (utile per la paginazione)

## Ricerca e lettura

> Ricerca e lettura di oggetti

```python

ids = odoo.env['ngo.donor'].search_read([
    ('email', 'like','gmail.com')
], ['name', 'email'])

print(ids)

```

```php
$ids = $odoo->env['ngo.donor']->search_read([
    ['email','like','gmail.com']
], ['name', 'email'])

print_r(ids)

```

> Risposta

```python
# lista di _id_ relativi alla ricerca
[
    {
        'id': 12345,
        'name': 'Tizio',
        'email': 'tizio@gmail.com'
    },
    {
        'id': 12346,
        'name': 'Caio',
        'email': 'caio@gmail.com'
    },
    {
        'id': 12347,
        'name': 'Sempronio',
        'email': 'sempronio@gmail.com'
    },
]
```

```php
# lista di _id_ relativi alla ricerca
[
    [
        'id' => 12345,
        'name' => 'Tizio',
        'email' => 'tizio@gmail.com'
    ],
    [
        'id' => 12346,
        'name' => 'Caio',
        'email' => 'caio@gmail.com'
    ],
    [
        'id' => 12347,
        'name' => 'Sempronio',
        'email' => 'sempronio@gmail.com'
    ],
]
```


E' possibile effettuare ricerche su un determato insieme di oggetti e farse restituire direttamente il valore di alcuni campi per diminuire il numero di richieste nessarie. Per farlo si ricorre al metodo _search\_read_

### search_read(domain, fields, limit, offset)

* **domain:** esprime il dominio della ricerca, e' una lista di tuple composte da _campo_,_operatore_,_valore_
* **fields:** lista dei campi da restituire
* **limit:** il numero massimo di elementi da restituire nella ricerca
* **offset:** l'offset da cui partire nei risultati (utile per la paginazione)

## Conteggio oggetti

> Contare quanti utenti hanno una mail gmail.com

```python

count = odoo.env['ngo.donor'].search_count([
    ('email', 'like','gmail.com')
])

print(count)

```

```php
$count = $odoo->env['ngo.donor']->search_count([
    ['email','like','gmail.com']
])

print_r(icount)

```

> Risposta

```
42 # Numero di ogggetti trovati relativi al _domain_ usato
```


E' possibile contare quanti oggetti rispondono a determinati criteri di ricerca. Per farlo si ricorre al metodo _search\_count_

### search_count(domain)

* **domain:** esprime il dominio della ricerca, e' una lista di tuple composte da _campo_,_operatore_,_valore_

## Modifica

> Modificare un oggetto

```python

donor_id = odoo.env['ngo.donor'].browse(12345)

donor_id.write({
    'email': 'test@test.it',
    'phone': '0551234567s'
})

```

```php
$donor_id = $odoo->env['ngo.donor']->browse(12345)
$donor_id->write([
    'email' => 'test@test.it',
    'phone' => '0551234567s'
])

```


E' possibile modificare i dati relativi ad un oggetto utilizzando il metodo _write_

### write(values)

* **values:** dizionario di valori con cui modificare l'oggetto


## Cancellazione

> Eliminare definitivamente un oggetto

```python

donor_id = odoo.env['ngo.donor'].browse(12345)
donor_id.unlink()

```

```php
$donor_id = $odoo->env['ngo.donor']->browse(12345)
$donor_id->unlink()

```


E' possibile eliminare un oggetto utilizzando il metodo _unlink_

### unlink()
