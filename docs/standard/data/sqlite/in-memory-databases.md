---
title: Database in memoria
ms.date: 12/13/2019
description: Informazioni su come usare i database SQLite in memoria.
ms.openlocfilehash: b125ff5aa4128bd4c3ff558c5573b7d11802090a
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75447244"
---
# <a name="in-memory-databases"></a>Database in memoria

I database in memoria SQLite sono database archiviati interamente in memoria, non su disco. Usare il nome file dell'origine dati speciale `:memory:` per creare un database in memoria. Quando la connessione viene chiusa, il database viene eliminato. Quando si utilizza `:memory:`, ogni connessione crea il proprio database.

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a>Database in memoria condivisibili

I database in memoria possono essere condivisi tra più connessioni usando `Mode=Memory` e `Cache=Shared` nella stringa di connessione. La parola chiave `Data Source` viene usata per assegnare un nome al database in memoria. Le stringhe di connessione con lo stesso nome otterranno l'accesso allo stesso database in memoria. Il database viene mantenuto finché almeno una connessione rimane aperta. Un [esempio](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) che illustra questa operazione è disponibile su GitHub.

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
