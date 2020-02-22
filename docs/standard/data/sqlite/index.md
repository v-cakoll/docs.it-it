---
title: Panoramica
ms.date: 12/13/2019
description: Panoramica di Microsoft. Data. sqlite
ms.openlocfilehash: e84c68f0615f187e8dea7ab87ac917c0ad796a1c
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543599"
---
# <a name="microsoftdatasqlite-overview"></a>Panoramica di Microsoft. Data. sqlite

Microsoft. Data. SQLite è un provider [ADO.NET](../../../framework/data/adonet/index.md) leggero per SQLite. Il provider di [Entity Framework Core](/ef/core/) per SQLite si basa su questa libreria. Tuttavia, può anche essere usato in modo indipendente o con altre librerie di accesso ai dati.

## <a name="installation"></a>Installazione

La versione stabile più recente è disponibile in [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite).

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

Questa libreria implementa le astrazioni ADO.NET comuni per le connessioni, i comandi, i lettori di dati e così via.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_HelloWorld)]

## <a name="see-also"></a>Vedere anche

* [Stringhe di connessione](connection-strings.md)
* [Informazioni di riferimento sulle API](/dotnet/api/?view=msdata-sqlite-3.0)
* [Sintassi SQL](https://www.sqlite.org/lang.html)
