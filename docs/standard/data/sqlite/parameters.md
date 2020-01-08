---
title: Parametri
ms.date: 12/13/2019
description: Informazioni su come usare i parametri SQL.
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75447188"
---
# <a name="parameters"></a><span data-ttu-id="3fbcd-103">Parametri</span><span class="sxs-lookup"><span data-stu-id="3fbcd-103">Parameters</span></span>

<span data-ttu-id="3fbcd-104">I parametri vengono usati per la protezione da attacchi SQL injection.</span><span class="sxs-lookup"><span data-stu-id="3fbcd-104">Parameters are used to protect against SQL injection attacks.</span></span> <span data-ttu-id="3fbcd-105">Anziché concatenare l'input dell'utente con istruzioni SQL, usare i parametri per garantire che l'input venga trattato solo come valore letterale e mai eseguito.</span><span class="sxs-lookup"><span data-stu-id="3fbcd-105">Instead of concatenating user input with SQL statements, use parameters to ensure input is only ever treated as a literal value and never executed.</span></span> <span data-ttu-id="3fbcd-106">In SQLite i parametri sono in genere consentiti ovunque sia consentito un valore letterale nelle istruzioni SQL.</span><span class="sxs-lookup"><span data-stu-id="3fbcd-106">In SQLite, parameters are typically allowed anywhere a literal is allowed in SQL statements.</span></span>

<span data-ttu-id="3fbcd-107">I parametri possono essere preceduti da `:`, `@`o `$`.</span><span class="sxs-lookup"><span data-stu-id="3fbcd-107">Parameters can be prefixed with either `:`, `@`, or `$`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

<span data-ttu-id="3fbcd-108">Per informazioni dettagliate su come viene eseguito il mapping dei valori .NET ai valori SQLite, vedere [tipi di dati](types.md) .</span><span class="sxs-lookup"><span data-stu-id="3fbcd-108">See [Data types](types.md) for details about how .NET values are mapped to SQLite values.</span></span>

## <a name="truncation"></a><span data-ttu-id="3fbcd-109">Troncamento</span><span class="sxs-lookup"><span data-stu-id="3fbcd-109">Truncation</span></span>

<span data-ttu-id="3fbcd-110">Utilizzare la proprietà <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> per troncare i valori di testo e BLOB.</span><span class="sxs-lookup"><span data-stu-id="3fbcd-110">Use the <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> property to truncate TEXT and BLOB values.</span></span>

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a><span data-ttu-id="3fbcd-111">Tipi alternativi</span><span class="sxs-lookup"><span data-stu-id="3fbcd-111">Alternative types</span></span>

<span data-ttu-id="3fbcd-112">In alcuni casi può essere utile usare un tipo SQLite alternativo.</span><span class="sxs-lookup"><span data-stu-id="3fbcd-112">Sometimes, you may want to use an alternative SQLite type.</span></span> <span data-ttu-id="3fbcd-113">A tale scopo, impostare la proprietà <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType>.</span><span class="sxs-lookup"><span data-stu-id="3fbcd-113">Do this by setting the <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> property.</span></span>

<span data-ttu-id="3fbcd-114">È possibile utilizzare i mapping di tipi alternativi seguenti.</span><span class="sxs-lookup"><span data-stu-id="3fbcd-114">The following alternative type mappings can be used.</span></span> <span data-ttu-id="3fbcd-115">Per i mapping predefiniti, vedere [tipi di dati](types.md).</span><span class="sxs-lookup"><span data-stu-id="3fbcd-115">For the default mappings, see [Data types](types.md).</span></span>

| <span data-ttu-id="3fbcd-116">Valore</span><span class="sxs-lookup"><span data-stu-id="3fbcd-116">Value</span></span>          | <span data-ttu-id="3fbcd-117">SqliteType</span><span class="sxs-lookup"><span data-stu-id="3fbcd-117">SqliteType</span></span> | <span data-ttu-id="3fbcd-118">Note</span><span class="sxs-lookup"><span data-stu-id="3fbcd-118">Remarks</span></span>          |
| -------------- | ---------- | ---------------- |
| <span data-ttu-id="3fbcd-119">Char</span><span class="sxs-lookup"><span data-stu-id="3fbcd-119">Char</span></span>           | <span data-ttu-id="3fbcd-120">Integer</span><span class="sxs-lookup"><span data-stu-id="3fbcd-120">Integer</span></span>    | <span data-ttu-id="3fbcd-121">UTF-16</span><span class="sxs-lookup"><span data-stu-id="3fbcd-121">UTF-16</span></span>           |
| <span data-ttu-id="3fbcd-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="3fbcd-122">DateTime</span></span>       | <span data-ttu-id="3fbcd-123">Real</span><span class="sxs-lookup"><span data-stu-id="3fbcd-123">Real</span></span>       | <span data-ttu-id="3fbcd-124">Valore di Julian Day</span><span class="sxs-lookup"><span data-stu-id="3fbcd-124">Julian day value</span></span> |
| <span data-ttu-id="3fbcd-125">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="3fbcd-125">DateTimeOffset</span></span> | <span data-ttu-id="3fbcd-126">Real</span><span class="sxs-lookup"><span data-stu-id="3fbcd-126">Real</span></span>       | <span data-ttu-id="3fbcd-127">Valore di Julian Day</span><span class="sxs-lookup"><span data-stu-id="3fbcd-127">Julian day value</span></span> |
| <span data-ttu-id="3fbcd-128">GUID</span><span class="sxs-lookup"><span data-stu-id="3fbcd-128">Guid</span></span>           | <span data-ttu-id="3fbcd-129">Blob</span><span class="sxs-lookup"><span data-stu-id="3fbcd-129">Blob</span></span>       |                  |
| <span data-ttu-id="3fbcd-130">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="3fbcd-130">TimeSpan</span></span>       | <span data-ttu-id="3fbcd-131">Real</span><span class="sxs-lookup"><span data-stu-id="3fbcd-131">Real</span></span>       | <span data-ttu-id="3fbcd-132">In giorni</span><span class="sxs-lookup"><span data-stu-id="3fbcd-132">In days</span></span>          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a><span data-ttu-id="3fbcd-133">Parametri di output</span><span class="sxs-lookup"><span data-stu-id="3fbcd-133">Output parameters</span></span>

<span data-ttu-id="3fbcd-134">SQLite non supporta i parametri di output.</span><span class="sxs-lookup"><span data-stu-id="3fbcd-134">SQLite doesn't support output parameters.</span></span> <span data-ttu-id="3fbcd-135">Restituire invece i valori nei risultati della query.</span><span class="sxs-lookup"><span data-stu-id="3fbcd-135">Return values in the query results instead.</span></span>

## <a name="see-also"></a><span data-ttu-id="3fbcd-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fbcd-136">See also</span></span>

* [<span data-ttu-id="3fbcd-137">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="3fbcd-137">Data types</span></span>](types.md)
