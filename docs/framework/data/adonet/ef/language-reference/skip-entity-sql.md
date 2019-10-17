---
title: SKIP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
ms.openlocfilehash: 75140384823588b8f6785de00b0ab3cd17314a3f
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319334"
---
# <a name="skip-entity-sql"></a><span data-ttu-id="b9613-102">SKIP (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b9613-102">SKIP (Entity SQL)</span></span>

<span data-ttu-id="b9613-103">Il paging fisico può essere eseguito usando la sottoclausola SKIP nella clausola ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="b9613-103">You can perform physical paging by using the SKIP sub-clause in the ORDER BY clause.</span></span> <span data-ttu-id="b9613-104">Non è possibile usare SKIP separatamente dalla clausola ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="b9613-104">SKIP cannot be used separately from the ORDER BY clause.</span></span>

## <a name="syntax"></a><span data-ttu-id="b9613-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b9613-105">Syntax</span></span>

```sql
[ SKIP n ]
```

## <a name="arguments"></a><span data-ttu-id="b9613-106">argomenti</span><span class="sxs-lookup"><span data-stu-id="b9613-106">Arguments</span></span>

`n` \
<span data-ttu-id="b9613-107">Numero di elementi da ignorare.</span><span class="sxs-lookup"><span data-stu-id="b9613-107">The number of items to skip.</span></span>

## <a name="remarks"></a><span data-ttu-id="b9613-108">Note</span><span class="sxs-lookup"><span data-stu-id="b9613-108">Remarks</span></span>

<span data-ttu-id="b9613-109">Se una sottoclausola dell'espressione SKIP è presente in una clausola ORDER BY, i risultati verranno ordinati in base alla specifica di ordinamento e il set di risultati includerà le righe a partire dalla riga immediatamente successiva all'espressione SKIP.</span><span class="sxs-lookup"><span data-stu-id="b9613-109">If a SKIP expression sub-clause is present in an ORDER BY clause, the results will be sorted according the sort specification and the result set will include rows starting from the next row immediately after the SKIP expression.</span></span> <span data-ttu-id="b9613-110">SKIP 5, ad esempio, consente di ignorare le prime cinque righe e restituisce le righe a partire dalla sesta in avanti.</span><span class="sxs-lookup"><span data-stu-id="b9613-110">For example, SKIP 5 will skip the first five rows and return from the sixth row forward.</span></span>

> [!NOTE]
> <span data-ttu-id="b9613-111">Una query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] viene considerata non valida se nella stessa espressione di query sono presenti sia il modificatore TOP che la sottoclausola SKIP.</span><span class="sxs-lookup"><span data-stu-id="b9613-111">An [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query is invalid if both the TOP modifier and the SKIP sub-clause are present in the same query expression.</span></span> <span data-ttu-id="b9613-112">È necessario riscrivere la query modificando l'espressione TOP nell'espressione LIMIT.</span><span class="sxs-lookup"><span data-stu-id="b9613-112">The query should be rewritten by changing the TOP expression to the LIMIT expression.</span></span>

> [!NOTE]
> <span data-ttu-id="b9613-113">In SQL Server 2000, l'uso di SKIP con ORDER BY in colonne non chiave può restituire risultati non corretti.</span><span class="sxs-lookup"><span data-stu-id="b9613-113">In SQL Server 2000, using SKIP with ORDER BY on non-key columns might return incorrect results.</span></span> <span data-ttu-id="b9613-114">Se la colonna non chiave include dati duplicati, potrebbe venire ignorato un numero di righe maggiore di quello specificato.</span><span class="sxs-lookup"><span data-stu-id="b9613-114">More than the specified number of rows might be skipped if the non-key column has duplicate data in it.</span></span> <span data-ttu-id="b9613-115">Ciò è dovuto alla modalità di conversione di SKIP per SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="b9613-115">This is due to how SKIP is translated for SQL Server 2000.</span></span> <span data-ttu-id="b9613-116">Nel codice seguente potrebbero ad esempio venire ignorate più di cinque righe se `E.NonKeyColumn` include valori duplicati:</span><span class="sxs-lookup"><span data-stu-id="b9613-116">For example, in the following code more than five rows might be skipped if `E.NonKeyColumn` has duplicate values:</span></span>
>
> ```sql
> SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L
> ```

<span data-ttu-id="b9613-117">La query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] in [procedura: pagina tramite i risultati della query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)) utilizza l'operatore ORDER BY con Skip per specificare l'ordinamento utilizzato per gli oggetti restituiti in un'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="b9613-117">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query in [How to: Page Through Query Results](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)) uses the ORDER BY operator with SKIP to specify the sort order used on objects returned in a SELECT statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9613-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9613-118">See also</span></span>

- [<span data-ttu-id="b9613-119">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="b9613-119">ORDER BY</span></span>](order-by-entity-sql.md)
- <span data-ttu-id="b9613-120">[Procedura: pagina tramite i risultati della query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b9613-120">[How to: Page Through Query Results](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>
- [<span data-ttu-id="b9613-121">Paging</span><span class="sxs-lookup"><span data-stu-id="b9613-121">Paging</span></span>](paging-entity-sql.md)
- [<span data-ttu-id="b9613-122">TOP</span><span class="sxs-lookup"><span data-stu-id="b9613-122">TOP</span></span>](top-entity-sql.md)
