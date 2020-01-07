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
# <a name="async-limitations"></a>Limitazioni asincrone

SQLite non supporta l'I/O asincrono. I metodi async ADO.NET vengono eseguiti in modo sincrono in Microsoft. Data. sqlite. Evitare di chiamarli.

Usare invece la [registrazione write-ahead](https://www.sqlite.org/wal.html) per migliorare le prestazioni e la concorrenza.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AsyncSample/Program.cs?name=snippet_WAL)]

> [!TIP]
> La registrazione write-ahead è abilitata per impostazione predefinita nei database creati con [Entity Framework Core](/ef/core/).
