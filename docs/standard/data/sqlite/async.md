---
title: Limitazioni asincrone
ms.date: 12/13/2019
description: Vengono illustrate le limitazioni delle API asincrone e alcune alternative che è possibile utilizzare.
ms.openlocfilehash: 350237dc5c03023f60e9680e8b9c94aabb62606f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75447083"
---
# <a name="async-limitations"></a><span data-ttu-id="b801d-103">Limitazioni asincrone</span><span class="sxs-lookup"><span data-stu-id="b801d-103">Async limitations</span></span>

<span data-ttu-id="b801d-104">SQLite non supporta l'I/O asincrono.</span><span class="sxs-lookup"><span data-stu-id="b801d-104">SQLite doesn't support asynchronous I/O.</span></span> <span data-ttu-id="b801d-105">I metodi async ADO.NET vengono eseguiti in modo sincrono in Microsoft. Data. sqlite.</span><span class="sxs-lookup"><span data-stu-id="b801d-105">Async ADO.NET methods will execute synchronously in Microsoft.Data.Sqlite.</span></span> <span data-ttu-id="b801d-106">Evitare di chiamarli.</span><span class="sxs-lookup"><span data-stu-id="b801d-106">Avoid calling them.</span></span>

<span data-ttu-id="b801d-107">Usare invece la [registrazione write-ahead](https://www.sqlite.org/wal.html) per migliorare le prestazioni e la concorrenza.</span><span class="sxs-lookup"><span data-stu-id="b801d-107">Instead, use [write-ahead logging](https://www.sqlite.org/wal.html) to improve performance and concurrency.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AsyncSample/Program.cs?name=snippet_WAL)]

> [!TIP]
> <span data-ttu-id="b801d-108">La registrazione write-ahead è abilitata per impostazione predefinita nei database creati con [Entity Framework Core](/ef/core/).</span><span class="sxs-lookup"><span data-stu-id="b801d-108">Write-ahead logging is enabled by default on databases created using [Entity Framework Core](/ef/core/).</span></span>
