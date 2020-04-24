---
title: Errori del database
ms.date: 12/13/2019
description: Viene descritto il modo in cui gli errori e i ritiri del database vengono gestiti dalla libreria.
ms.openlocfilehash: 9a613b6f94a89dc40e627c14f46836be77080035
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75447272"
---
# <a name="database-errors"></a>Errori del database

<xref:Microsoft.Data.Sqlite.SqliteException>viene generata quando viene rilevato un errore SQLite. Il messaggio viene fornito da SQLite. Le `SqliteErrorCode` proprietà `SqliteExtendedErrorCode` e contengono il [codice di risultato](https://www.sqlite.org/rescode.html) SQLite dell'errore.

Gli errori possono essere rilevati ogni volta che Microsoft. Data. sqlite interagisce con la libreria SQLite nativa. Nell'elenco seguente vengono illustrati gli scenari comuni in cui possono verificarsi errori:

* Apertura di una connessione.
* Inizio di una transazione.
* Esecuzione di un comando.
* Tramite chiamata a <xref:Microsoft.Data.Sqlite.SqliteDataReader.NextResult%2A>.

Valutare attentamente il modo in cui l'app gestirà questi errori.

## <a name="locking-retries-and-timeouts"></a>Blocco, tentativi e timeout

SQLite è molto aggressivo quando si tratta di tabelle di blocco e di file di database. Se l'app consente l'accesso a un database simultaneo, è probabile che si verifichino errori di occupato e bloccato. È possibile attenuare molti errori usando una [cache condivisa](connection-strings.md#cache) e una [registrazione write-ahead](async.md).

Ogni volta che Microsoft. Data. sqlite rileva un errore occupato o bloccato, verrà ritentato automaticamente finché non avrà esito positivo o verrà raggiunto il timeout del comando.

È possibile aumentare il timeout del comando impostando <xref:Microsoft.Data.Sqlite.SqliteCommand.CommandTimeout%2A>. Il timeout predefinito è 30 secondi. Il valore `0` indica nessun timeout.

```csharp
// Retry for 60 seconds while locked
command.CommandTimeout = 60;
```

Microsoft. Data. sqlite a volte deve creare un oggetto comando implicito. Ad esempio, durante BeginTransaction. Per impostare il timeout per questi comandi, utilizzare <xref:Microsoft.Data.Sqlite.SqliteConnection.DefaultTimeout%2A>.

```csharp
// Set the default timeout of all commands on this connection
connection.DefaultTimeout = 60;
```

## <a name="see-also"></a>Vedi anche

* [Codici di errore SQLite](https://www.sqlite.org/rescode.html)
* [Blocco di file in SQLite](https://www.sqlite.org/lockingv3.html)
* [Modalità cache condivisa](https://www.sqlite.org/sharedcache.html)
* [Registrazione write-ahead](https://www.sqlite.org/wal.html)
