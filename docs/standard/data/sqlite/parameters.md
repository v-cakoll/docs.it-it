---
title: Parametri
ms.date: 12/13/2019
description: Informazioni su come usare i parametri SQL.
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400456"
---
# <a name="parameters"></a><span data-ttu-id="8dac6-103">Parametri</span><span class="sxs-lookup"><span data-stu-id="8dac6-103">Parameters</span></span>

<span data-ttu-id="8dac6-104">I parametri vengono utilizzati per la protezione da attacchi SQL injection.</span><span class="sxs-lookup"><span data-stu-id="8dac6-104">Parameters are used to protect against SQL injection attacks.</span></span> <span data-ttu-id="8dac6-105">Anziché concatenare l'input dell'utente con istruzioni SQL, usare i parametri per garantire che l'input venga considerato solo come valore letterale e non venga mai eseguito.</span><span class="sxs-lookup"><span data-stu-id="8dac6-105">Instead of concatenating user input with SQL statements, use parameters to ensure input is only ever treated as a literal value and never executed.</span></span> <span data-ttu-id="8dac6-106">In SQLite, i parametri sono in genere consentiti ovunque sia consentito un valore letterale nelle istruzioni SQL.</span><span class="sxs-lookup"><span data-stu-id="8dac6-106">In SQLite, parameters are typically allowed anywhere a literal is allowed in SQL statements.</span></span>

<span data-ttu-id="8dac6-107">I parametri possono essere `:` `@`preceduti `$`dal prefisso , , o .</span><span class="sxs-lookup"><span data-stu-id="8dac6-107">Parameters can be prefixed with either `:`, `@`, or `$`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

<span data-ttu-id="8dac6-108">Vedere [tipi di dati](types.md) per informazioni dettagliate su come i valori .NET vengono mappati ai valori SQLite.See Data types for details about how .NET values are mapped to SQLite values.</span><span class="sxs-lookup"><span data-stu-id="8dac6-108">See [Data types](types.md) for details about how .NET values are mapped to SQLite values.</span></span>

## <a name="truncation"></a><span data-ttu-id="8dac6-109">Troncamento</span><span class="sxs-lookup"><span data-stu-id="8dac6-109">Truncation</span></span>

<span data-ttu-id="8dac6-110">Utilizzare <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> la proprietà per troncare i valori TEXT e BLOB.</span><span class="sxs-lookup"><span data-stu-id="8dac6-110">Use the <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> property to truncate TEXT and BLOB values.</span></span>

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a><span data-ttu-id="8dac6-111">Tipi alternativi</span><span class="sxs-lookup"><span data-stu-id="8dac6-111">Alternative types</span></span>

<span data-ttu-id="8dac6-112">A volte, è possibile utilizzare un tipo SQLite alternativo.</span><span class="sxs-lookup"><span data-stu-id="8dac6-112">Sometimes, you may want to use an alternative SQLite type.</span></span> <span data-ttu-id="8dac6-113">A tale scopo, impostare la <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="8dac6-113">Do this by setting the <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> property.</span></span>

<span data-ttu-id="8dac6-114">È possibile utilizzare i seguenti mapping di tipi alternativi.</span><span class="sxs-lookup"><span data-stu-id="8dac6-114">The following alternative type mappings can be used.</span></span> <span data-ttu-id="8dac6-115">Per i mapping predefiniti, vedere [Tipi di dati](types.md).</span><span class="sxs-lookup"><span data-stu-id="8dac6-115">For the default mappings, see [Data types](types.md).</span></span>

| <span data-ttu-id="8dac6-116">valore</span><span class="sxs-lookup"><span data-stu-id="8dac6-116">Value</span></span>          | <span data-ttu-id="8dac6-117">SqliteType (TipoSqliteType)</span><span class="sxs-lookup"><span data-stu-id="8dac6-117">SqliteType</span></span> | <span data-ttu-id="8dac6-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8dac6-118">Remarks</span></span>          |
| -------------- | ---------- | ---------------- |
| <span data-ttu-id="8dac6-119">Char</span><span class="sxs-lookup"><span data-stu-id="8dac6-119">Char</span></span>           | <span data-ttu-id="8dac6-120">Integer</span><span class="sxs-lookup"><span data-stu-id="8dac6-120">Integer</span></span>    | <span data-ttu-id="8dac6-121">UTF-16</span><span class="sxs-lookup"><span data-stu-id="8dac6-121">UTF-16</span></span>           |
| <span data-ttu-id="8dac6-122">Datetime</span><span class="sxs-lookup"><span data-stu-id="8dac6-122">DateTime</span></span>       | <span data-ttu-id="8dac6-123">Real</span><span class="sxs-lookup"><span data-stu-id="8dac6-123">Real</span></span>       | <span data-ttu-id="8dac6-124">Valore del giorno giuliano</span><span class="sxs-lookup"><span data-stu-id="8dac6-124">Julian day value</span></span> |
| <span data-ttu-id="8dac6-125">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="8dac6-125">DateTimeOffset</span></span> | <span data-ttu-id="8dac6-126">Real</span><span class="sxs-lookup"><span data-stu-id="8dac6-126">Real</span></span>       | <span data-ttu-id="8dac6-127">Valore del giorno giuliano</span><span class="sxs-lookup"><span data-stu-id="8dac6-127">Julian day value</span></span> |
| <span data-ttu-id="8dac6-128">Guid</span><span class="sxs-lookup"><span data-stu-id="8dac6-128">Guid</span></span>           | <span data-ttu-id="8dac6-129">BLOB</span><span class="sxs-lookup"><span data-stu-id="8dac6-129">Blob</span></span>       |                  |
| <span data-ttu-id="8dac6-130">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="8dac6-130">TimeSpan</span></span>       | <span data-ttu-id="8dac6-131">Real</span><span class="sxs-lookup"><span data-stu-id="8dac6-131">Real</span></span>       | <span data-ttu-id="8dac6-132">In giorni</span><span class="sxs-lookup"><span data-stu-id="8dac6-132">In days</span></span>          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a><span data-ttu-id="8dac6-133">Parametri di output</span><span class="sxs-lookup"><span data-stu-id="8dac6-133">Output parameters</span></span>

<span data-ttu-id="8dac6-134">SQLite non supporta i parametri di output.</span><span class="sxs-lookup"><span data-stu-id="8dac6-134">SQLite doesn't support output parameters.</span></span> <span data-ttu-id="8dac6-135">Restituisce invece i valori nei risultati della query.</span><span class="sxs-lookup"><span data-stu-id="8dac6-135">Return values in the query results instead.</span></span>

## <a name="see-also"></a><span data-ttu-id="8dac6-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8dac6-136">See also</span></span>

* [<span data-ttu-id="8dac6-137">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="8dac6-137">Data types</span></span>](types.md)
