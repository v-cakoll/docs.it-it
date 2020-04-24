---
title: Limitazioni di ADO.NET
ms.date: 12/13/2019
description: Descrive alcune delle limitazioni di ADO.NET che possono verificarsi.
ms.openlocfilehash: 8664b73071fc859ed30080f549b05e7d6ed020f4
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901256"
---
# <a name="adonet-limitations"></a><span data-ttu-id="7c220-103">Limitazioni di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7c220-103">ADO.NET limitations</span></span>

<span data-ttu-id="7c220-104">Microsoft. Data. SQLite fornisce le implementazioni di molte delle astrazioni ADO.NET, ma esistono alcune limitazioni.</span><span class="sxs-lookup"><span data-stu-id="7c220-104">Microsoft.Data.Sqlite provides implementations of many of the ADO.NET abstractions, but there are some limitations.</span></span>

## <a name="database-schema-information"></a><span data-ttu-id="7c220-105">Informazioni sullo schema del database</span><span class="sxs-lookup"><span data-stu-id="7c220-105">Database schema information</span></span>

<span data-ttu-id="7c220-106">I metadati relativi ai risultati della query sono <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> disponibili tramite il metodo.</span><span class="sxs-lookup"><span data-stu-id="7c220-106">Metadata about query results is available using the <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> method.</span></span>

<span data-ttu-id="7c220-107">`DbConnection.GetSchema()`non è implementato.</span><span class="sxs-lookup"><span data-stu-id="7c220-107">`DbConnection.GetSchema()` isn't implemented.</span></span> <span data-ttu-id="7c220-108">Questa API non è ben definita, quindi è consigliabile recuperare i metadati del database direttamente usando le API SQLite standard come la tabella [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) e il [TABLE_INFO](https://www.sqlite.org/pragma.html#pragma_table_info) pragma.</span><span class="sxs-lookup"><span data-stu-id="7c220-108">This API isn't well-defined, so we recommend retrieving database metadata directly using standard SQLite APIs like the [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) table and the [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) PRAGMA.</span></span>

<span data-ttu-id="7c220-109">Per ulteriori informazioni, vedere [metadati](metadata.md).</span><span class="sxs-lookup"><span data-stu-id="7c220-109">For more information, see [Metadata](metadata.md).</span></span>

## <a name="systemtransactions"></a><span data-ttu-id="7c220-110">System.Transactions</span><span class="sxs-lookup"><span data-stu-id="7c220-110">System.Transactions</span></span>

<span data-ttu-id="7c220-111">Microsoft. Data. SQLite non supporta ancora System. Transactions.</span><span class="sxs-lookup"><span data-stu-id="7c220-111">Microsoft.Data.Sqlite doesn't yet support System.Transactions.</span></span> <span data-ttu-id="7c220-112">Usare invece le transazioni ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="7c220-112">Use ADO.NET transactions instead.</span></span> <span data-ttu-id="7c220-113">Per altre informazioni, vedere [Transazioni](transactions.md).</span><span class="sxs-lookup"><span data-stu-id="7c220-113">For more information, see [Transactions](transactions.md).</span></span>

<span data-ttu-id="7c220-114">Inviare commenti e suggerimenti sulla mancanza di supporto per System. Transactions sul problema [#13825](https://github.com/dotnet/efcore/issues/13825).</span><span class="sxs-lookup"><span data-stu-id="7c220-114">Provide feedback about the lack of support for System.Transactions on issue [#13825](https://github.com/dotnet/efcore/issues/13825).</span></span>

## <a name="data-adapters"></a><span data-ttu-id="7c220-115">Adattatori dati</span><span class="sxs-lookup"><span data-stu-id="7c220-115">Data adapters</span></span>

<span data-ttu-id="7c220-116">`DbDataAdapter`non è ancora implementato da Microsoft. Data. sqlite.</span><span class="sxs-lookup"><span data-stu-id="7c220-116">`DbDataAdapter` isn't yet implemented by Microsoft.Data.Sqlite.</span></span> <span data-ttu-id="7c220-117">Ciò significa che è possibile usare solo `DataSet` ADO.NET `DataTable` e caricare i dati e non aggiornarli.</span><span class="sxs-lookup"><span data-stu-id="7c220-117">This means you can only use ADO.NET `DataSet` and `DataTable` to load data and not update it.</span></span>

<span data-ttu-id="7c220-118">Usare [#13838](https://github.com/dotnet/efcore/issues/13838) di problema per fornire commenti e `DbDataAdapter`suggerimenti sull'implementazione di.</span><span class="sxs-lookup"><span data-stu-id="7c220-118">Use issue [#13838](https://github.com/dotnet/efcore/issues/13838) to provide feedback about implementing `DbDataAdapter`.</span></span>

## <a name="output-parameters"></a><span data-ttu-id="7c220-119">Parametri di output</span><span class="sxs-lookup"><span data-stu-id="7c220-119">Output parameters</span></span>

<span data-ttu-id="7c220-120">SQLite non supporta i parametri di output.</span><span class="sxs-lookup"><span data-stu-id="7c220-120">SQLite doesn't support output parameters.</span></span>

## <a name="positional-parameters"></a><span data-ttu-id="7c220-121">Parametri posizionali</span><span class="sxs-lookup"><span data-stu-id="7c220-121">Positional parameters</span></span>

<span data-ttu-id="7c220-122">Microsoft. Data. SQLite supporta solo i [parametri](parameters.md)denominati.</span><span class="sxs-lookup"><span data-stu-id="7c220-122">Microsoft.Data.Sqlite only supports named [parameters](parameters.md).</span></span> <span data-ttu-id="7c220-123">I parametri posizionali non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="7c220-123">Positional parameters aren't supported.</span></span>

## <a name="stored-procedures"></a><span data-ttu-id="7c220-124">Stored procedure</span><span class="sxs-lookup"><span data-stu-id="7c220-124">Stored procedures</span></span>

<span data-ttu-id="7c220-125">SQLite non supporta le stored procedure.</span><span class="sxs-lookup"><span data-stu-id="7c220-125">SQLite doesn't support stored procedures.</span></span>

## <a name="isolation-levels"></a><span data-ttu-id="7c220-126">Livelli di isolamento</span><span class="sxs-lookup"><span data-stu-id="7c220-126">Isolation levels</span></span>

<span data-ttu-id="7c220-127">I `Chaos` livelli `Snapshot` di isolamento e non sono supportati nelle transazioni SQLite.</span><span class="sxs-lookup"><span data-stu-id="7c220-127">The `Chaos` and `Snapshot` isolation levels aren't supported in SQLite transactions.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c220-128">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="7c220-128">See also</span></span>

* [<span data-ttu-id="7c220-129">Limitazioni asincrone</span><span class="sxs-lookup"><span data-stu-id="7c220-129">Async limitations</span></span>](async.md)
* [<span data-ttu-id="7c220-130">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="7c220-130">Data types</span></span>](types.md)
* [<span data-ttu-id="7c220-131">Transazioni</span><span class="sxs-lookup"><span data-stu-id="7c220-131">Transactions</span></span>](transactions.md)
