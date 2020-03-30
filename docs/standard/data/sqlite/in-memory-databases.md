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
# <a name="in-memory-databases"></a><span data-ttu-id="c7953-103">Database in memoria</span><span class="sxs-lookup"><span data-stu-id="c7953-103">In-memory databases</span></span>

<span data-ttu-id="c7953-104">I database In memoria di SQLite sono database archiviati interamente in memoria, non su disco.</span><span class="sxs-lookup"><span data-stu-id="c7953-104">SQLite in-memory databases are databases stored entirely in memory, not on disk.</span></span> <span data-ttu-id="c7953-105">Utilizzare il nome `:memory:` file dell'origine dati speciale per creare un database in memoria.</span><span class="sxs-lookup"><span data-stu-id="c7953-105">Use the special data source filename `:memory:` to create an in-memory database.</span></span> <span data-ttu-id="c7953-106">Quando la connessione viene chiusa, il database viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="c7953-106">When the connection is closed, the database is deleted.</span></span> <span data-ttu-id="c7953-107">Quando `:memory:`si utilizza , ogni connessione crea il proprio database.</span><span class="sxs-lookup"><span data-stu-id="c7953-107">When using `:memory:`, each connection creates its own database.</span></span>

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a><span data-ttu-id="c7953-108">Database in memoria condissoperabili</span><span class="sxs-lookup"><span data-stu-id="c7953-108">Shareable in-memory databases</span></span>

<span data-ttu-id="c7953-109">I database in memoria possono essere `Mode=Memory` condivisi `Cache=Shared` tra più connessioni utilizzando e nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="c7953-109">In-memory databases can be shared between multiple connections by using `Mode=Memory` and `Cache=Shared` in the connection string.</span></span> <span data-ttu-id="c7953-110">La `Data Source` parola chiave viene utilizzata per assegnare un nome al database in memoria.</span><span class="sxs-lookup"><span data-stu-id="c7953-110">The `Data Source` keyword is used to give the in-memory database a name.</span></span> <span data-ttu-id="c7953-111">Le stringhe di connessione che utilizzano lo stesso nome accederanno allo stesso database in memoria.</span><span class="sxs-lookup"><span data-stu-id="c7953-111">Connection strings using the same name will access the same in-memory database.</span></span> <span data-ttu-id="c7953-112">Il database persiste finché almeno una connessione ad esso rimane aperta.</span><span class="sxs-lookup"><span data-stu-id="c7953-112">The database persists as long as at least one connection to it remains open.</span></span> <span data-ttu-id="c7953-113">Un esempio che dimostra questo è disponibile su GitHub.A [sample](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) demonstrating this is available on GitHub.</span><span class="sxs-lookup"><span data-stu-id="c7953-113">A [sample](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) demonstrating this is available on GitHub.</span></span>

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
