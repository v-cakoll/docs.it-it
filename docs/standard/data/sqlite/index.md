---
title: Panoramica di
ms.date: 12/13/2019
description: Panoramica di Microsoft. Data. sqlite
ms.openlocfilehash: a5dc1366cc0ddfcd5501e26bf2a994456bcd5d98
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75447230"
---
# <a name="microsoftdatasqlite-overview"></a>Panoramica di Microsoft. Data. sqlite

Microsoft. Data. SQLite è un provider [ADO.NET](../../../framework/data/adonet/index.md) leggero per SQLite. Il provider di [Entity Framework Core](/ef/core/) per SQLite si basa su questa libreria. Tuttavia, può anche essere usato in modo indipendente o con altre librerie di accesso ai dati.

## <a name="installation"></a>Installazione di

La versione stabile più recente è disponibile in [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite).

### <a name="net-core-clitabnetcore-cli"></a>[Interfaccia della riga di comando di .NET Core](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite
```

### <a name="visual-studiotabvisual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite
```

---

## <a name="usage"></a>Usage

Questa libreria implementa le astrazioni ADO.NET comuni per le connessioni, i comandi, i lettori di dati e così via.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_HelloWorld)]

## <a name="see-also"></a>Vedere anche

* [Stringhe di connessione](connection-strings.md)
* [Riferimento API](/dotnet/api/?view=msdata-sqlite-3.0.0)
* [Sintassi SQL](https://www.sqlite.org/lang.html)
