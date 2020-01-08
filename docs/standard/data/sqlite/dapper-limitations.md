---
title: Limitazioni di elegante
ms.date: 12/13/2019
description: Descrive alcune delle limitazioni che si verificheranno quando si usa l'elegante.
ms.openlocfilehash: 90c7fb24f068d663081390bdba9b1b222b4be56e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75447279"
---
# <a name="dapper-limitations"></a><span data-ttu-id="29431-103">Limitazioni di elegante</span><span class="sxs-lookup"><span data-stu-id="29431-103">Dapper limitations</span></span>

<span data-ttu-id="29431-104">Quando si usa Microsoft. Data. sqlite con [elegante](https://stackexchange.github.io/Dapper/), è necessario tenere presenti alcune limitazioni.</span><span class="sxs-lookup"><span data-stu-id="29431-104">There are a few limitations you should be aware of when using Microsoft.Data.Sqlite with [Dapper](https://stackexchange.github.io/Dapper/).</span></span>

## <a name="parameters"></a><span data-ttu-id="29431-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="29431-105">Parameters</span></span>

<span data-ttu-id="29431-106">I nomi dei parametri SQLite fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="29431-106">SQLite parameter names are case-sensitive.</span></span> <span data-ttu-id="29431-107">Verificare che i nomi di parametro usati in SQL corrispondano al caso delle proprietà dell'oggetto anonimo.</span><span class="sxs-lookup"><span data-stu-id="29431-107">Ensure that the parameter names used in SQL match the case of the anonymous object's properties.</span></span> <span data-ttu-id="29431-108">Il problema [#18861](https://github.com/aspnet/EntityFrameworkCore/issues/18861) potrebbe migliorare questa esperienza.</span><span class="sxs-lookup"><span data-stu-id="29431-108">Issue [#18861](https://github.com/aspnet/EntityFrameworkCore/issues/18861) would improve this experience.</span></span>

<span data-ttu-id="29431-109">L'utilizzo del prefisso `@` è previsto anche per i parametri.</span><span class="sxs-lookup"><span data-stu-id="29431-109">Dapper also expects parameters to use the `@` prefix.</span></span> <span data-ttu-id="29431-110">Gli altri prefissi non funzioneranno.</span><span class="sxs-lookup"><span data-stu-id="29431-110">Other prefixes won't work.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_Parameter)]

## <a name="data-types"></a><span data-ttu-id="29431-111">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="29431-111">Data types</span></span>

<span data-ttu-id="29431-112">Elegante legge i valori usando l'indicizzatore SqliteDataReader.</span><span class="sxs-lookup"><span data-stu-id="29431-112">Dapper reads values using the SqliteDataReader indexer.</span></span> <span data-ttu-id="29431-113">Il tipo restituito di questo indicizzatore è Object, il che significa che restituirà solo valori Long, Double, String o byte [].</span><span class="sxs-lookup"><span data-stu-id="29431-113">The return type of this indexer is object, which means it will only ever return long, double, string, or byte[] values.</span></span> <span data-ttu-id="29431-114">Per ulteriori informazioni, vedere [tipi di dati](types.md).</span><span class="sxs-lookup"><span data-stu-id="29431-114">For more information, see [Data types](types.md).</span></span> <span data-ttu-id="29431-115">L'elegante gestisce la maggior parte delle conversioni tra questi e altri tipi primitivi.</span><span class="sxs-lookup"><span data-stu-id="29431-115">Dapper handles most conversions between these and other primitive types.</span></span> <span data-ttu-id="29431-116">Sfortunatamente, non gestisce `DateTimeOffset`, `Guid`o `TimeSpan`.</span><span class="sxs-lookup"><span data-stu-id="29431-116">Unfortunately, it doesn't handle `DateTimeOffset`, `Guid`, or `TimeSpan`.</span></span> <span data-ttu-id="29431-117">Creare gestori di tipi se si vuole usare questi tipi nei risultati.</span><span class="sxs-lookup"><span data-stu-id="29431-117">Create type handlers if you want to use these types in your results.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_TypeHandlers)]

<span data-ttu-id="29431-118">Non dimenticare di aggiungere i gestori di tipi prima di eseguire una query.</span><span class="sxs-lookup"><span data-stu-id="29431-118">Don't forget to add the type handlers before querying.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_AddTypeHandlers)]

## <a name="see-also"></a><span data-ttu-id="29431-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29431-119">See also</span></span>

* [<span data-ttu-id="29431-120">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="29431-120">Data types</span></span>](types.md)
* [<span data-ttu-id="29431-121">Limitazioni asincrone</span><span class="sxs-lookup"><span data-stu-id="29431-121">Async limitations</span></span>](async.md)
