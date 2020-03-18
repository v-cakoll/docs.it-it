---
title: Stringhe di connessione
ms.date: 12/13/2019
description: Parole chiave supportate e valori delle stringhe di connessione.
ms.openlocfilehash: bb54d152bac62a86c2a49192cf678a745159164e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400449"
---
# <a name="connection-strings"></a>Stringhe di connessione

Una stringa di connessione viene utilizzata per specificare come connettersi al database. Le stringhe di connessione in Microsoft.Data.Sqlite seguono la [sintassi standard ADO.NET](../../../framework/data/adonet/connection-strings.md) come elenco separato da punti e virgola di parole chiave e valori.

## <a name="keywords"></a>Parole chiave

Le parole chiave della stringa di connessione seguenti possono essere utilizzate con Microsoft.Data.Sqlite:The following connection string keywords can be used with Microsoft.Data.Sqlite:

### <a name="data-source"></a>Origine dati

Percorso del file di database. *DataSource* (senza spazi) e *Filename* sono alias di questa parola chiave.

SQLite considera i percorsi relativi alla directory di lavoro corrente. È inoltre possibile specificare percorsi assoluti.

Se **vuoto**, SQLite crea un database temporaneo su disco che viene eliminato quando la connessione viene chiusa.

Se `:memory:`è , viene utilizzato un database in memoria. Per ulteriori informazioni, vedere [Database in memoria](in-memory-databases.md).

I percorsi `|DataDirectory|` che iniziano con la stringa di sostituzione vengono considerati allo stesso modo dei percorsi relativi. Se impostato, i percorsi vengono resi relativi al valore della proprietà del dominio applicazione DataDirectory.

Questa parola chiave supporta anche [URI Filenames](https://www.sqlite.org/uri.html).

### <a name="mode"></a>Mode

Modalità di connessione.

| valore           | Descrizione                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| ReadWriteCreate | Apre il database per la lettura e la scrittura e lo crea se non esiste. Questa è la modalità predefinita. |
| ReadWrite       | Apre il database per la lettura e la scrittura.                                                        |
| ReadOnly        | Apre il database in modalità di sola lettura.                                                              |
| Memoria          | Apre un database in memoria.                                                                       |

### <a name="cache"></a>Cache

Modalità di memorizzazione nella cache utilizzata dalla connessione.

| valore   | Descrizione                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| Predefinito | Utilizza la modalità predefinita della libreria SQLite sottostante. Questa è la modalità predefinita.                   |
| Privato | Ogni connessione utilizza una cache privata.                                                          |
| Condiviso  | Le connessioni condividono una cache. Questa modalità può modificare il comportamento delle transazioni e del blocco delle tabelle. |

### <a name="password"></a>Password

Chiave di crittografia. Se specificato, `PRAGMA key` viene inviato immediatamente dopo l'apertura della connessione.

> [!WARNING]
> La password non ha effetto quando la crittografia non è supportata dalla libreria SQLite nativa.

### <a name="foreign-keys"></a>Chiavi esterne

Valore che indica se abilitare i vincoli di chiave esterna.

| valore   | Descrizione
| ------- | --- |
| True     | Invia `PRAGMA foreign_keys = 1` subito dopo l'apertura della connessione.
| False   | Invia `PRAGMA foreign_keys = 0` subito dopo l'apertura della connessione.
| (vuoto) | Non invia `PRAGMA foreign_keys`. Questa è la modalità predefinita. |

Non è necessario abilitare le chiavi esterne se, come in e_sqlite3, è stato usato SQLITE_DEFAULT_FOREIGN_KEYS per compilare la libreria SQLite nativa.

### <a name="recursive-triggers"></a>Trigger ricorsivi

Valore che indica se abilitare i trigger ricorsivi.

| valore | Descrizione                                                                 |
| ----- | --------------------------------------------------------------------------- |
| True   | Invia `PRAGMA recursive_triggers` subito dopo l'apertura della connessione. |
| False | Non invia `PRAGMA recursive_triggers`. Questa è la modalità predefinita.              |

## <a name="connection-string-builder"></a>Generatore di stringhe di connessioneConnection string builder

È possibile <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> utilizzare un modo fortemente tipizzato di creare stringhe di connessione. Può anche essere utilizzato per prevenire attacchi di iniezione stringa di connessione.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a>Esempi

### <a name="basic"></a>Basic

Stringa di connessione di base con una cache condivisa per una migliore concorrenza.

```ConnectionString
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a>Crittografato

Un database crittografato.

```ConnectionString
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a>Sola lettura

Database di sola lettura che non può essere modificato dall'app.

```ConnectionString
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a>In memoria

Un database privato in memoria.

```ConnectionString
Data Source=:memory:
```

### <a name="sharable-in-memory"></a>Sharable in-memory

Database condivisibili e in memoria identificato con il nome *Sharable*.

```ConnectionString
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a>Vedere anche

* [Stringhe di connessione in ADO.NET](../../../framework/data/adonet/connection-strings.md)
* [Database in memoria](in-memory-databases.md)
* [Transazioni](transactions.md)
