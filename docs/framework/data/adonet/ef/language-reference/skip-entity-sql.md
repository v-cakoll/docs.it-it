---
title: SKIP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
ms.openlocfilehash: b6335086ce5b61cf23db2bf967d1a82f322e83b3
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70043629"
---
# <a name="skip-entity-sql"></a><span data-ttu-id="8eb7f-102">SKIP (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8eb7f-102">SKIP (Entity SQL)</span></span>

<span data-ttu-id="8eb7f-103">Il paging fisico può essere eseguito usando la sottoclausola SKIP nella clausola ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="8eb7f-103">You can perform physical paging by using the SKIP sub-clause in the ORDER BY clause.</span></span> <span data-ttu-id="8eb7f-104">Non è possibile usare SKIP separatamente dalla clausola ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="8eb7f-104">SKIP cannot be used separately from the ORDER BY clause.</span></span>

## <a name="syntax"></a><span data-ttu-id="8eb7f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8eb7f-105">Syntax</span></span>

```
[ SKIP n ]
```

## <a name="arguments"></a><span data-ttu-id="8eb7f-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="8eb7f-106">Arguments</span></span>

`n` \
<span data-ttu-id="8eb7f-107">Numero di elementi da ignorare.</span><span class="sxs-lookup"><span data-stu-id="8eb7f-107">The number of items to skip.</span></span>

## <a name="remarks"></a><span data-ttu-id="8eb7f-108">Note</span><span class="sxs-lookup"><span data-stu-id="8eb7f-108">Remarks</span></span>

<span data-ttu-id="8eb7f-109">Se una sottoclausola dell'espressione SKIP è presente in una clausola ORDER BY, i risultati verranno ordinati in base alla specifica di ordinamento e il set di risultati includerà le righe a partire dalla riga immediatamente successiva all'espressione SKIP.</span><span class="sxs-lookup"><span data-stu-id="8eb7f-109">If a SKIP expression sub-clause is present in an ORDER BY clause, the results will be sorted according the sort specification and the result set will include rows starting from the next row immediately after the SKIP expression.</span></span> <span data-ttu-id="8eb7f-110">SKIP 5, ad esempio, consente di ignorare le prime cinque righe e restituisce le righe a partire dalla sesta in avanti.</span><span class="sxs-lookup"><span data-stu-id="8eb7f-110">For example, SKIP 5 will skip the first five rows and return from the sixth row forward.</span></span>

> [!NOTE]
> <span data-ttu-id="8eb7f-111">Una query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] viene considerata non valida se nella stessa espressione di query sono presenti sia il modificatore TOP che la sottoclausola SKIP.</span><span class="sxs-lookup"><span data-stu-id="8eb7f-111">An [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query is invalid if both the TOP modifier and the SKIP sub-clause are present in the same query expression.</span></span> <span data-ttu-id="8eb7f-112">È necessario riscrivere la query modificando l'espressione TOP nell'espressione LIMIT.</span><span class="sxs-lookup"><span data-stu-id="8eb7f-112">The query should be rewritten by changing the TOP expression to the LIMIT expression.</span></span>

> [!NOTE]
> <span data-ttu-id="8eb7f-113">In SQL Server 2000, l'uso di SKIP con ORDER BY in colonne non chiave può restituire risultati non corretti.</span><span class="sxs-lookup"><span data-stu-id="8eb7f-113">In SQL Server 2000, using SKIP with ORDER BY on non-key columns might return incorrect results.</span></span> <span data-ttu-id="8eb7f-114">Se la colonna non chiave include dati duplicati, potrebbe venire ignorato un numero di righe maggiore di quello specificato.</span><span class="sxs-lookup"><span data-stu-id="8eb7f-114">More than the specified number of rows might be skipped if the non-key column has duplicate data in it.</span></span> <span data-ttu-id="8eb7f-115">Ciò è dovuto alla modalità di conversione di SKIP per SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="8eb7f-115">This is due to how SKIP is translated for SQL Server 2000.</span></span> <span data-ttu-id="8eb7f-116">Nel codice seguente potrebbero ad esempio venire ignorate più di cinque righe se `E.NonKeyColumn` include valori duplicati:</span><span class="sxs-lookup"><span data-stu-id="8eb7f-116">For example, in the following code more than five rows might be skipped if `E.NonKeyColumn` has duplicate values:</span></span>
>
> `SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L`

<span data-ttu-id="8eb7f-117">La [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query in [procedura: La pagina tramite i](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)) risultati della query usa l'operatore ORDER BY con Skip per specificare l'ordinamento usato per gli oggetti restituiti in un'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="8eb7f-117">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query in [How to: Page Through Query Results](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)) uses the ORDER BY operator with SKIP to specify the sort order used on objects returned in a SELECT statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="8eb7f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8eb7f-118">See also</span></span>

- [<span data-ttu-id="8eb7f-119">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="8eb7f-119">ORDER BY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)
- <span data-ttu-id="8eb7f-120">[Procedura: Pagina tramite i risultati della query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8eb7f-120">[How to: Page Through Query Results](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>
- [<span data-ttu-id="8eb7f-121">Paging</span><span class="sxs-lookup"><span data-stu-id="8eb7f-121">Paging</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)
- [<span data-ttu-id="8eb7f-122">TOP</span><span class="sxs-lookup"><span data-stu-id="8eb7f-122">TOP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
