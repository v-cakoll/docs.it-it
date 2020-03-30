---
title: Database in memoria
ms.date: 12/13/2019
description: Informazioni su come utilizzare i database SQLite in memoria.
ms.openlocfilehash: 408c81f538e27dcfffad20db74b7809912b7905f
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391208"
---
# <a name="in-memory-databases"></a>Database in memoria

I database In memoria di SQLite sono database archiviati interamente in memoria, non su disco. Utilizzare il nome `:memory:` file dell'origine dati speciale per creare un database in memoria. Quando la connessione viene chiusa, il database viene eliminato. Quando `:memory:`si utilizza , ogni connessione crea il proprio database.

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a>Database in memoria condissoperabili

I database in memoria possono essere `Mode=Memory` condivisi `Cache=Shared` tra più connessioni utilizzando e nella stringa di connessione. La `Data Source` parola chiave viene utilizzata per assegnare un nome al database in memoria. Le stringhe di connessione che utilizzano lo stesso nome accederanno allo stesso database in memoria. Il database persiste finché almeno una connessione ad esso rimane aperta. Un esempio che dimostra questo è disponibile su GitHub.A [sample](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) demonstrating this is available on GitHub.

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
