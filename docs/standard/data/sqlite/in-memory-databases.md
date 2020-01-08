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
# <a name="in-memory-databases"></a><span data-ttu-id="a34d0-103">Database in memoria</span><span class="sxs-lookup"><span data-stu-id="a34d0-103">In-memory databases</span></span>

<span data-ttu-id="a34d0-104">I database in memoria SQLite sono database archiviati interamente in memoria, non su disco.</span><span class="sxs-lookup"><span data-stu-id="a34d0-104">SQLite in-memory databases are databases stored entirely in memory, not on disk.</span></span> <span data-ttu-id="a34d0-105">Usare il nome file dell'origine dati speciale `:memory:` per creare un database in memoria.</span><span class="sxs-lookup"><span data-stu-id="a34d0-105">Use the special data source filename `:memory:` to create an in-memory database.</span></span> <span data-ttu-id="a34d0-106">Quando la connessione viene chiusa, il database viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="a34d0-106">When the connection is closed, the database is deleted.</span></span> <span data-ttu-id="a34d0-107">Quando si utilizza `:memory:`, ogni connessione crea il proprio database.</span><span class="sxs-lookup"><span data-stu-id="a34d0-107">When using `:memory:`, each connection creates its own database.</span></span>

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a><span data-ttu-id="a34d0-108">Database in memoria condivisibili</span><span class="sxs-lookup"><span data-stu-id="a34d0-108">Shareable in-memory databases</span></span>

<span data-ttu-id="a34d0-109">I database in memoria possono essere condivisi tra più connessioni usando `Mode=Memory` e `Cache=Shared` nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="a34d0-109">In-memory databases can be shared between multiple connections by using `Mode=Memory` and `Cache=Shared` in the connection string.</span></span> <span data-ttu-id="a34d0-110">La parola chiave `Data Source` viene usata per assegnare un nome al database in memoria.</span><span class="sxs-lookup"><span data-stu-id="a34d0-110">The `Data Source` keyword is used to give the in-memory database a name.</span></span> <span data-ttu-id="a34d0-111">Le stringhe di connessione con lo stesso nome otterranno l'accesso allo stesso database in memoria.</span><span class="sxs-lookup"><span data-stu-id="a34d0-111">Connection strings using the same name will access the same in-memory database.</span></span> <span data-ttu-id="a34d0-112">Il database viene mantenuto finché almeno una connessione rimane aperta.</span><span class="sxs-lookup"><span data-stu-id="a34d0-112">The database persists as long as at least one connection to it remains open.</span></span> <span data-ttu-id="a34d0-113">Un [esempio](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) che illustra questa operazione è disponibile su GitHub.</span><span class="sxs-lookup"><span data-stu-id="a34d0-113">A [sample](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) demonstrating this is available on GitHub.</span></span>

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
