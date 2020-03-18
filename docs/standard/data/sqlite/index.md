---
title: Panoramica
ms.date: 12/13/2019
description: Panoramica di Microsoft.Data.Sqlite
ms.openlocfilehash: e84c68f0615f187e8dea7ab87ac917c0ad796a1c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "77543599"
---
# <a name="microsoftdatasqlite-overview"></a>Panoramica di Microsoft.Data.Sqlite

Microsoft.Data.Sqlite è un provider [di ADO.NET](../../../framework/data/adonet/index.md) leggero per SQLite.Microsoft.Data.Sqlite is a lightweight ADO.NET provider for SQLite. Il provider [Entity Framework Core](/ef/core/) per SQLite si basa su questa libreria. Tuttavia, può anche essere utilizzato in modo indipendente o con altre librerie di accesso ai dati.

## <a name="installation"></a>Installazione

L'ultima versione stabile è disponibile su [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite).

### <a name="net-core-cli"></a>[Interfaccia della riga di comando di .NET Core](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite
```

### <a name="visual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite
```

---

## <a name="usage"></a>Uso

Questa libreria implementa le astrazioni comuni ADO.NET per connessioni, comandi, lettori dati e così via.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_HelloWorld)]

## <a name="see-also"></a>Vedere anche

* [Stringhe di connessione](connection-strings.md)
* [Riferimento API](/dotnet/api/?view=msdata-sqlite-3.0)
* [Sintassi SQL](https://www.sqlite.org/lang.html)
