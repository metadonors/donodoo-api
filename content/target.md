---
weight: 60
title: Liste
---

# Liste 

> Lettura di una lista

```python
target_id = odoo.env['ngo.target'].browse(12345)
```

```php
$target_id = $odoo->env['ngo.target']->browse(12345)
```

L'insieme degli oggetti liste risponde alla risorsa **ngo.target**


<!-- add_donors_by_ids -->

```python
target_id = odoo.env['ngo.target'].browse(12345)
target_id.add_donors_by_ids([123, 456, 789])
```

```php
$target_id = $odoo->env['ngo.target']->browse(12345)
$target_id->add_donors_by_ids([123, 456, 789])
```

## Aggiungi donatori
### add_donors_by_ids(ids)

Aggiunge donotori alla lista.

* **ids:** lista di _id_ donatore da aggiungere alla lista

<!-- remove_donors_by_ids -->

```python
target_id = odoo.env['ngo.target'].browse(12345)
target_id.remove_donors_by_ids([123, 456, 789])
```

```php
$target_id = $odoo->env['ngo.target']->browse(12345)
$target_id->remove_donors_by_ids([123, 456, 789])
```

## Rimuovi donatori
### remove_donors_by_ids(ids)

Rimuove donotori alla lista.

* **ids:** lista di _id_ donatore da rimuovere dalla lista

<!-- add_subscriptions_by_ids -->

```python
target_id = odoo.env['ngo.target'].browse(12345)
target_id.add_subscriptions_by_ids([123, 456, 789])
```

```php
$target_id = $odoo->env['ngo.target']->browse(12345)
$target_id->add_subscriptions_by_ids([123, 456, 789])
```

## Aggiungi deleghe
### add_subscriptions_by_ids(ids)

Aggiunge deleghe alla lista.

* **ids:** lista di _id_ delega da aggiungere alla lista

<!-- remove_subscriptions_by_ids -->

```python
target_id = odoo.env['ngo.target'].browse(12345)
target_id.remove_subscriptions_by_ids([123, 456, 789])
```

```php
$target_id = $odoo->env['ngo.target']->browse(12345)
$target_id->remove_subscriptions_by_ids([123, 456, 789])
```

## Rimuovi deleghe
### remove_subscriptions_by_ids(ids)

Rimuove deleghe alla lista.

* **ids:** lista di _id_ delega da rimuovere dalla lista
