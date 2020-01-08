---
title: Stringhe di connessione
ms.date: 12/13/2019
description: Parole chiave e valori supportati delle stringhe di connessione.
ms.openlocfilehash: bb54d152bac62a86c2a49192cf678a745159164e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75447013"
---
# <a name="connection-strings"></a>Stringhe di connessione

Una stringa di connessione viene utilizzata per specificare la modalità di connessione al database. Le stringhe di connessione in Microsoft. Data. sqlite seguono la [sintassi ADO.NET](../../../framework/data/adonet/connection-strings.md) standard come un elenco di parole chiave e valori delimitati da punto e virgola.

## <a name="keywords"></a>Parole chiave

Con Microsoft. Data. SQLite è possibile usare le parole chiave della stringa di connessione seguenti:

### <a name="data-source"></a>Origine dati

Percorso del file di database. *DataSource* (senza spazio) e *filename* sono alias di questa parola chiave.

SQLite considera i percorsi relativi alla directory di lavoro corrente. È anche possibile specificare percorsi assoluti.

Se **vuoto**, SQLite crea un database su disco temporaneo che viene eliminato alla chiusura della connessione.

Se `:memory:`, viene utilizzato un database in memoria. Per ulteriori informazioni, vedere [database in memoria](in-memory-databases.md).

I percorsi che iniziano con la stringa di sostituzione `|DataDirectory|` vengono considerati uguali ai percorsi relativi. Se impostata, i percorsi vengono eseguiti in relazione al valore della proprietà del dominio dell'applicazione DataDirectory.

Questa parola chiave supporta anche i [nomi file URI](https://www.sqlite.org/uri.html).

### <a name="mode"></a>Modalità

Modalità di connessione.

| Valore           | Descrizione                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| ReadWriteCreate | Apre il database per la lettura e la scrittura e lo crea se non esiste. Questo è il valore predefinito. |
| ReadWrite       | Apre il database per la lettura e la scrittura.                                                        |
| ReadOnly        | Apre il database in modalità di sola lettura.                                                              |
| Memoria          | Apre un database in memoria.                                                                       |

### <a name="cache"></a>Cache

Modalità di memorizzazione nella cache utilizzata dalla connessione.

| Valore   | Descrizione                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| Default | Usa la modalità predefinita della libreria SQLite sottostante. Questo è il valore predefinito.                   |
| Private | Ogni connessione utilizza una cache privata.                                                          |
| Condivisa  | Le connessioni condividono una cache. Questa modalità può modificare il comportamento di blocco delle transazioni e della tabella. |

### <a name="password"></a>Password

Chiave di crittografia. Se specificato, `PRAGMA key` viene inviato immediatamente dopo l'apertura della connessione.

> [!WARNING]
> La password non ha alcun effetto se la crittografia non è supportata dalla libreria SQLite nativa.

### <a name="foreign-keys"></a>Chiavi esterne

Valore che indica se abilitare i vincoli di chiave esterna.

| Valore   | Descrizione
| ------- | --- |
| True    | Invia `PRAGMA foreign_keys = 1` immediatamente dopo l'apertura della connessione.
| Falso   | Invia `PRAGMA foreign_keys = 0` immediatamente dopo l'apertura della connessione.
| (vuoto) | Non invia `PRAGMA foreign_keys`. Questo è il valore predefinito. |

Non è necessario abilitare le chiavi esterne se, come in e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS è stato usato per compilare la libreria SQLite nativa.

### <a name="recursive-triggers"></a>Trigger ricorsivi

Valore che indica se abilitare i trigger ricorsivi.

| Valore | Descrizione                                                                 |
| ----- | --------------------------------------------------------------------------- |
| True  | Invia `PRAGMA recursive_triggers` immediatamente dopo l'apertura della connessione. |
| Falso | Non invia `PRAGMA recursive_triggers`. Questo è il valore predefinito.              |

## <a name="connection-string-builder"></a>Generatore di stringhe di connessione

È possibile utilizzare <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> come modo fortemente tipizzato per la creazione di stringhe di connessione. Può anche essere usato per impedire attacchi injection alla stringa di connessione.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a>Esempi

### <a name="basic"></a>Basic

Stringa di connessione di base con una cache condivisa per una maggiore concorrenza.

```ConnectionString
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a>Crittografato

Un database crittografato.

```ConnectionString
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a>Sola lettura

Un database di sola lettura che non può essere modificato dall'app.

```ConnectionString
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a>In memoria

Un database privato in memoria.

```ConnectionString
Data Source=:memory:
```

### <a name="sharable-in-memory"></a>Condivisibile in memoria

Un database condivisibile in memoria identificato dal nome *condivisibile*.

```ConnectionString
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a>Vedere anche

* [Stringhe di connessione in ADO.NET](../../../framework/data/adonet/connection-strings.md)
* [Database in memoria](in-memory-databases.md)
* [Transazioni](transactions.md)
