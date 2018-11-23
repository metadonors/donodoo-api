---
weight: 40
title: Campagne
---

# Campagne

> Lettura di una campagna

```python
campaign_id = odoo.env['ngo.campaign'].browse(12345)
```

```php
$campaign_id = $odoo->env['ngo.campaign']->browse(12345)
```

L'insieme degli oggetti campagna risponde alla risorsa **ngo.campaign**



<!-- open -->

```python
campaign_id = odoo.env['ngo.campaign'].browse(12345)
campaign_id.open()
```

```php
$campaign_id = $odoo->env['ngo.campaign']->browse(12345)
$campaign_id->open()
```

## Apri campagna
### open()

Sposta una campagna dallo stato _Bozza_ allo stato _Aperto_. Se presenti [donatori](#donatori) nella [lista](#liste) assiciata crea automaticamente le [lavorazioni](#lavorazioni) relative.

<!-- close -->

```python
campaign_id = odoo.env['ngo.campaign'].browse(12345)
campaign_id.close()
```

```php
$campaign_id = $odoo->env['ngo.campaign']->browse(12345)
$campaign_id->close()
```

## Chiudi campagna
### close()

Sposta una campagna dallo stato _Aperto_ allo stato _Chiuso_. Se presenti [Lavorazioni](#lavorazioni) non ancora completate le annulla automaticamente.


<!-- add_donors_by_ids -->

```python
campaign_id = odoo.env['ngo.campaign'].browse(12345)
campaign_id.add_donors_by_ids([123, 456, 789])
```

```php
$campaign_id = $odoo->env['ngo.campaign']->browse(12345)
$campaign_id->add_donors_by_ids([123, 456, 789])
```

## Aggiungi donatori
### add_donors_by_ids(ids)

Aggiunge donotori alla lista legata alla campagna. Se non e' presente la lista ne crea una di default. Se la campagna e' in stato _Aperto_ vengono automaticamente generate le lavorazioni.

* **ids:** lista di _id_ donatore da aggiungere alla lista della campagna

