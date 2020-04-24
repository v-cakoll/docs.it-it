---
title: Database in memoria
ms.date: 12/13/2019
description: Informazioni su come usare i database SQLite in memoria.
ms.openlocfilehash: 408c81f538e27dcfffad20db74b7809912b7905f
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391208"
---
# <a name="in-memory-databases"></a>Database in memoria

I database in memoria SQLite sono database archiviati interamente in memoria, non su disco. Usare il nome file `:memory:` dell'origine dati speciale per creare un database in memoria. Quando la connessione viene chiusa, il database viene eliminato. Quando si `:memory:`utilizza, ogni connessione crea il proprio database.

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a>Database in memoria condivisibili

I database in memoria possono essere condivisi tra più connessioni utilizzando `Mode=Memory` e `Cache=Shared` nella stringa di connessione. La `Data Source` parola chiave viene usata per assegnare un nome al database in memoria. Le stringhe di connessione con lo stesso nome otterranno l'accesso allo stesso database in memoria. Il database viene mantenuto finché almeno una connessione rimane aperta. Un [esempio](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) che illustra questa operazione è disponibile su GitHub.

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
