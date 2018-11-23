---
weight: 2
title: Autenticazione
---


# Autenticazione


> Per effettuare il login, questo è il codice:

```python
import odoorpc

odoo = odoorpc.ODOO(host, port)

odoo.login(database, username, password)

user = odoo.env.user
print(user.name)            # name of the user connected
print(user.company_id.name) # the name of its company

```

```perl
use OdooRPCClient\Client;

$odoo = new Client($url);

$odoo->login($database, $username, $password);

$user = $odoo->env->user;

echo "{$user->name}\n";
echo "{$user->company_id->name}\n";

```

Prima di effettuare qualsiasi operazione tramite le API è necessario autenticarsi. Il tipo di operazioni che possono essere svolte dipendono dai permessi dell'utente utilizzato.

## Login
### login(database, username, password)

* **database:** database su cui autenticarsi
* **username:** nome utente
* **password:** password utente
