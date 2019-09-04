---
title: '- Dividere (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: ef48c368-f3ed-4275-8ada-4e9649781262
ms.openlocfilehash: d4e4c1449b665e6dea22bfcc0ee2277478b4da1a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251059"
---
# <a name="-divide-entity-sql"></a><span data-ttu-id="d8188-102">/ (divisione) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d8188-102">/ (Divide) (Entity SQL)</span></span>
<span data-ttu-id="d8188-103">Divide un numero per un altro.</span><span class="sxs-lookup"><span data-stu-id="d8188-103">Divides one number by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8188-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d8188-104">Syntax</span></span>  
  
```  
dividend / divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="d8188-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d8188-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="d8188-106">Espressione numerica da dividere.</span><span class="sxs-lookup"><span data-stu-id="d8188-106">The numeric expression to divide.</span></span> <span data-ttu-id="d8188-107">`dividend` è qualsiasi espressione valida con qualsiasi tipo di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="d8188-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="d8188-108">Espressione numerica per la quale dividere il dividendo.</span><span class="sxs-lookup"><span data-stu-id="d8188-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="d8188-109">`divisor` è qualsiasi espressione valida con qualsiasi tipo di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="d8188-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="d8188-110">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="d8188-110">Result Types</span></span>  
 <span data-ttu-id="d8188-111">Tipo di dati ottenuto della promozione implicita del tipo dei due argomenti.</span><span class="sxs-lookup"><span data-stu-id="d8188-111">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="d8188-112">Per ulteriori informazioni sull'innalzamento di tipo implicito, vedere [System Type](type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="d8188-112">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8188-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="d8188-113">Example</span></span>  
 <span data-ttu-id="d8188-114">Nella query Entity SQL seguente viene usato l'operatore aritmetico/per dividere un numero per un altro.</span><span class="sxs-lookup"><span data-stu-id="d8188-114">The following Entity SQL query uses the / arithmetic operator to divide one number by another.</span></span> <span data-ttu-id="d8188-115">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="d8188-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d8188-116">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8188-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="d8188-117">Attenersi alla procedura descritta [in procedura: Eseguire una query che restituisce i risultati](../how-to-execute-a-query-that-returns-structuraltype-results.md)di StructuralType.</span><span class="sxs-lookup"><span data-stu-id="d8188-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="d8188-118">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="d8188-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#DIVIDE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#divide)]  
  
## <a name="see-also"></a><span data-ttu-id="d8188-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8188-119">See also</span></span>

- [<span data-ttu-id="d8188-120">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d8188-120">Entity SQL Reference</span></span>](entity-sql-reference.md)
