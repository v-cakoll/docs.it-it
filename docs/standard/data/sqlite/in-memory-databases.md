---
title: Database in memoria
ms.date: 12/13/2019
description: Informazioni su come usare i database SQLite in memoria.
ms.openlocfilehash: 16a9b6536fbfede203c24b757e96e28e7c49dc05
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777405"
---
# <a name="in-memory-databases"></a><span data-ttu-id="0a76e-103">Database in memoria</span><span class="sxs-lookup"><span data-stu-id="0a76e-103">In-memory databases</span></span>

<span data-ttu-id="0a76e-104">I database in memoria SQLite sono database archiviati interamente in memoria, non su disco.</span><span class="sxs-lookup"><span data-stu-id="0a76e-104">SQLite in-memory databases are databases stored entirely in memory, not on disk.</span></span> <span data-ttu-id="0a76e-105">Usare il nome file dell'origine dati speciale `:memory:` per creare un database in memoria.</span><span class="sxs-lookup"><span data-stu-id="0a76e-105">Use the special data source filename `:memory:` to create an in-memory database.</span></span> <span data-ttu-id="0a76e-106">Quando la connessione viene chiusa, il database viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="0a76e-106">When the connection is closed, the database is deleted.</span></span> <span data-ttu-id="0a76e-107">Quando si utilizza `:memory:`, ogni connessione crea il proprio database.</span><span class="sxs-lookup"><span data-stu-id="0a76e-107">When using `:memory:`, each connection creates its own database.</span></span>

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a><span data-ttu-id="0a76e-108">Database in memoria condivisibili</span><span class="sxs-lookup"><span data-stu-id="0a76e-108">Shareable in-memory databases</span></span>

<span data-ttu-id="0a76e-109">I database in memoria possono essere condivisi tra più connessioni usando `Mode=Memory` e `Cache=Shared` nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="0a76e-109">In-memory databases can be shared between multiple connections by using `Mode=Memory` and `Cache=Shared` in the connection string.</span></span> <span data-ttu-id="0a76e-110">La parola chiave `Data Source` viene usata per assegnare un nome al database in memoria.</span><span class="sxs-lookup"><span data-stu-id="0a76e-110">The `Data Source` keyword is used to give the in-memory database a name.</span></span> <span data-ttu-id="0a76e-111">Le stringhe di connessione con lo stesso nome otterranno l'accesso allo stesso database in memoria.</span><span class="sxs-lookup"><span data-stu-id="0a76e-111">Connection strings using the same name will access the same in-memory database.</span></span> <span data-ttu-id="0a76e-112">Il database viene mantenuto finché almeno una connessione rimane aperta.</span><span class="sxs-lookup"><span data-stu-id="0a76e-112">The database persists as long as at least one connection to it remains open.</span></span> <span data-ttu-id="0a76e-113">Un [esempio](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/InMemorySample/Program.cs) che illustra questa operazione è disponibile su GitHub.</span><span class="sxs-lookup"><span data-stu-id="0a76e-113">A [sample](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/InMemorySample/Program.cs) demonstrating this is available on GitHub.</span></span>

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
