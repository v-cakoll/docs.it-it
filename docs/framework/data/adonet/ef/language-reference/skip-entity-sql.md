---
title: SKIP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
ms.openlocfilehash: b17f73f97d32f151ed4f51b025c0c5a7a97393bb
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2019
ms.locfileid: "55904173"
---
# <a name="skip-entity-sql"></a><span data-ttu-id="1edca-102">SKIP (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="1edca-102">SKIP (Entity SQL)</span></span>
<span data-ttu-id="1edca-103">Il paging fisico può essere eseguito usando la sottoclausola SKIP nella clausola ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="1edca-103">You can perform physical paging by using the SKIP sub-clause in the ORDER BY clause.</span></span> <span data-ttu-id="1edca-104">Non è possibile usare SKIP separatamente dalla clausola ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="1edca-104">SKIP cannot be used separately from the ORDER BY clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1edca-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1edca-105">Syntax</span></span>  
  
```  
[ SKIP n ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="1edca-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="1edca-106">Arguments</span></span>  
 `n`  
 <span data-ttu-id="1edca-107">Numero di elementi da ignorare.</span><span class="sxs-lookup"><span data-stu-id="1edca-107">The number of items to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1edca-108">Note</span><span class="sxs-lookup"><span data-stu-id="1edca-108">Remarks</span></span>  
 <span data-ttu-id="1edca-109">Se una sottoclausola dell'espressione SKIP è presente in una clausola ORDER BY, i risultati verranno ordinati in base alla specifica di ordinamento e il set di risultati includerà le righe a partire dalla riga immediatamente successiva all'espressione SKIP.</span><span class="sxs-lookup"><span data-stu-id="1edca-109">If a SKIP expression sub-clause is present in an ORDER BY clause, the results will be sorted according the sort specification and the result set will include rows starting from the next row immediately after the SKIP expression.</span></span> <span data-ttu-id="1edca-110">SKIP 5, ad esempio, consente di ignorare le prime cinque righe e restituisce le righe a partire dalla sesta in avanti.</span><span class="sxs-lookup"><span data-stu-id="1edca-110">For example, SKIP 5 will skip the first five rows and return from the sixth row forward.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1edca-111">Una query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] viene considerata non valida se nella stessa espressione di query sono presenti sia il modificatore TOP che la sottoclausola SKIP.</span><span class="sxs-lookup"><span data-stu-id="1edca-111">An [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query is invalid if both the TOP modifier and the SKIP sub-clause are present in the same query expression.</span></span> <span data-ttu-id="1edca-112">È necessario riscrivere la query modificando l'espressione TOP nell'espressione LIMIT.</span><span class="sxs-lookup"><span data-stu-id="1edca-112">The query should be rewritten by changing the TOP expression to the LIMIT expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1edca-113">In [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)]l'uso di SKIP con ORDER BY in colonne non chiave può restituire risultati non corretti.</span><span class="sxs-lookup"><span data-stu-id="1edca-113">In [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)], using SKIP with ORDER BY on non-key columns might return incorrect results.</span></span> <span data-ttu-id="1edca-114">Se la colonna non chiave include dati duplicati, potrebbe venire ignorato un numero di righe maggiore di quello specificato.</span><span class="sxs-lookup"><span data-stu-id="1edca-114">More than the specified number of rows might be skipped if the non-key column has duplicate data in it.</span></span> <span data-ttu-id="1edca-115">Questo comportamento è dovuto alla modalità di conversione di SKIP per [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1edca-115">This is due to how SKIP is translated for [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)].</span></span> <span data-ttu-id="1edca-116">Nel codice seguente potrebbero ad esempio venire ignorate più di cinque righe se `E.NonKeyColumn` include valori duplicati:</span><span class="sxs-lookup"><span data-stu-id="1edca-116">For example, in the following code more than five rows might be skipped if `E.NonKeyColumn` has duplicate values:</span></span>  
>   
>  `SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L`  
  
 <span data-ttu-id="1edca-117">Il [!INCLUDE[esql](../../../../../../includes/esql-md.md)] eseguire una query in [come: Pagina di risultati tramite Query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)) Usa l'operatore ORDER BY con SKIP per specificare l'ordinamento usato per gli oggetti restituiti in un'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="1edca-117">The  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query in [How to: Page Through Query Results](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)) uses the ORDER BY operator with SKIP to specify the sort order used on objects returned in a SELECT statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1edca-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1edca-118">See also</span></span>
- [<span data-ttu-id="1edca-119">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="1edca-119">ORDER BY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)
- <span data-ttu-id="1edca-120">[Procedura: Spostarsi tra i risultati della Query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1edca-120">[How to: Page Through Query Results](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>
- [<span data-ttu-id="1edca-121">Paging</span><span class="sxs-lookup"><span data-stu-id="1edca-121">Paging</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)
- [<span data-ttu-id="1edca-122">TOP</span><span class="sxs-lookup"><span data-stu-id="1edca-122">TOP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
