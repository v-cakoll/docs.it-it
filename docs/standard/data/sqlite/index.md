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
# <a name="microsoftdatasqlite-overview"></a><span data-ttu-id="19f85-103">Panoramica di Microsoft.Data.Sqlite</span><span class="sxs-lookup"><span data-stu-id="19f85-103">Microsoft.Data.Sqlite overview</span></span>

<span data-ttu-id="19f85-104">Microsoft.Data.Sqlite è un provider [di ADO.NET](../../../framework/data/adonet/index.md) leggero per SQLite.Microsoft.Data.Sqlite is a lightweight ADO.NET provider for SQLite.</span><span class="sxs-lookup"><span data-stu-id="19f85-104">Microsoft.Data.Sqlite is a lightweight [ADO.NET](../../../framework/data/adonet/index.md) provider for SQLite.</span></span> <span data-ttu-id="19f85-105">Il provider [Entity Framework Core](/ef/core/) per SQLite si basa su questa libreria.</span><span class="sxs-lookup"><span data-stu-id="19f85-105">The [Entity Framework Core](/ef/core/) provider for SQLite is built on top of this library.</span></span> <span data-ttu-id="19f85-106">Tuttavia, può anche essere utilizzato in modo indipendente o con altre librerie di accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="19f85-106">However, it can also be used independently or with other data access libraries.</span></span>

## <a name="installation"></a><span data-ttu-id="19f85-107">Installazione</span><span class="sxs-lookup"><span data-stu-id="19f85-107">Installation</span></span>

<span data-ttu-id="19f85-108">L'ultima versione stabile è disponibile su [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite).</span><span class="sxs-lookup"><span data-stu-id="19f85-108">The latest stable version is available on [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite).</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="19f85-109">Interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="19f85-109">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite
```

### <a name="visual-studio"></a>[<span data-ttu-id="19f85-110">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="19f85-110">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite
```

---

## <a name="usage"></a><span data-ttu-id="19f85-111">Uso</span><span class="sxs-lookup"><span data-stu-id="19f85-111">Usage</span></span>

<span data-ttu-id="19f85-112">Questa libreria implementa le astrazioni comuni ADO.NET per connessioni, comandi, lettori dati e così via.</span><span class="sxs-lookup"><span data-stu-id="19f85-112">This library implements the common ADO.NET abstractions for connections, commands, data readers, and so on.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_HelloWorld)]

## <a name="see-also"></a><span data-ttu-id="19f85-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19f85-113">See also</span></span>

* [<span data-ttu-id="19f85-114">Stringhe di connessione</span><span class="sxs-lookup"><span data-stu-id="19f85-114">Connection strings</span></span>](connection-strings.md)
* [<span data-ttu-id="19f85-115">Riferimento API</span><span class="sxs-lookup"><span data-stu-id="19f85-115">API Reference</span></span>](/dotnet/api/?view=msdata-sqlite-3.0)
* [<span data-ttu-id="19f85-116">Sintassi SQL</span><span class="sxs-lookup"><span data-stu-id="19f85-116">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
