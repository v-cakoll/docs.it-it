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
# <a name="microsoftdatasqlite-overview"></a><span data-ttu-id="c11d9-103">Panoramica di Microsoft. Data. sqlite</span><span class="sxs-lookup"><span data-stu-id="c11d9-103">Microsoft.Data.Sqlite overview</span></span>

<span data-ttu-id="c11d9-104">Microsoft. Data. SQLite è un provider [ADO.NET](../../../framework/data/adonet/index.md) leggero per SQLite.</span><span class="sxs-lookup"><span data-stu-id="c11d9-104">Microsoft.Data.Sqlite is a lightweight [ADO.NET](../../../framework/data/adonet/index.md) provider for SQLite.</span></span> <span data-ttu-id="c11d9-105">Il provider di [Entity Framework Core](/ef/core/) per SQLite si basa su questa libreria.</span><span class="sxs-lookup"><span data-stu-id="c11d9-105">The [Entity Framework Core](/ef/core/) provider for SQLite is built on top of this library.</span></span> <span data-ttu-id="c11d9-106">Tuttavia, può anche essere usato in modo indipendente o con altre librerie di accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="c11d9-106">However, it can also be used independently or with other data access libraries.</span></span>

## <a name="installation"></a><span data-ttu-id="c11d9-107">Installazione di</span><span class="sxs-lookup"><span data-stu-id="c11d9-107">Installation</span></span>

<span data-ttu-id="c11d9-108">La versione stabile più recente è disponibile in [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite).</span><span class="sxs-lookup"><span data-stu-id="c11d9-108">The latest stable version is available on [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite).</span></span>

### <a name="net-core-clitabnetcore-cli"></a>[<span data-ttu-id="c11d9-109">Interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="c11d9-109">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite
```

### <a name="visual-studiotabvisual-studio"></a>[<span data-ttu-id="c11d9-110">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c11d9-110">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite
```

---

## <a name="usage"></a><span data-ttu-id="c11d9-111">Usage</span><span class="sxs-lookup"><span data-stu-id="c11d9-111">Usage</span></span>

<span data-ttu-id="c11d9-112">Questa libreria implementa le astrazioni ADO.NET comuni per le connessioni, i comandi, i lettori di dati e così via.</span><span class="sxs-lookup"><span data-stu-id="c11d9-112">This library implements the common ADO.NET abstractions for connections, commands, data readers, and so on.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_HelloWorld)]

## <a name="see-also"></a><span data-ttu-id="c11d9-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c11d9-113">See also</span></span>

* [<span data-ttu-id="c11d9-114">Stringhe di connessione</span><span class="sxs-lookup"><span data-stu-id="c11d9-114">Connection strings</span></span>](connection-strings.md)
* [<span data-ttu-id="c11d9-115">Riferimento API</span><span class="sxs-lookup"><span data-stu-id="c11d9-115">API Reference</span></span>](/dotnet/api/?view=msdata-sqlite-3.0.0)
* [<span data-ttu-id="c11d9-116">Sintassi SQL</span><span class="sxs-lookup"><span data-stu-id="c11d9-116">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
