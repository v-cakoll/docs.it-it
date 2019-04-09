---
title: '- (Divisione) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: ef48c368-f3ed-4275-8ada-4e9649781262
ms.openlocfilehash: ca63835a3be23137a1a40d6d6597083ae2128ac7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094892"
---
# <a name="-divide-entity-sql"></a><span data-ttu-id="a4ac1-102">/ (divisione) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a4ac1-102">/ (Divide) (Entity SQL)</span></span>
<span data-ttu-id="a4ac1-103">Divide un numero per un altro.</span><span class="sxs-lookup"><span data-stu-id="a4ac1-103">Divides one number by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4ac1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a4ac1-104">Syntax</span></span>  
  
```  
dividend / divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="a4ac1-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a4ac1-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="a4ac1-106">Espressione numerica da dividere.</span><span class="sxs-lookup"><span data-stu-id="a4ac1-106">The numeric expression to divide.</span></span> `dividend` <span data-ttu-id="a4ac1-107">è qualsiasi espressione valida di uno dei tipi di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="a4ac1-107">is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="a4ac1-108">Espressione numerica per la quale dividere il dividendo.</span><span class="sxs-lookup"><span data-stu-id="a4ac1-108">The numeric expression to divide the dividend by.</span></span> `divisor` <span data-ttu-id="a4ac1-109">è qualsiasi espressione valida di uno dei tipi di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="a4ac1-109">is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="a4ac1-110">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="a4ac1-110">Result Types</span></span>  
 <span data-ttu-id="a4ac1-111">Tipo di dati ottenuto della promozione implicita del tipo dei due argomenti.</span><span class="sxs-lookup"><span data-stu-id="a4ac1-111">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="a4ac1-112">Per altre informazioni sulla promozione implicita del tipo, vedere [sistema di tipi](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a4ac1-112">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4ac1-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="a4ac1-113">Example</span></span>  
 <span data-ttu-id="a4ac1-114">Le query Entity SQL seguente viene usato l'aritmetico / per dividere un numero per un altro operatore.</span><span class="sxs-lookup"><span data-stu-id="a4ac1-114">The following Entity SQL query uses the / arithmetic operator to divide one number by another.</span></span> <span data-ttu-id="a4ac1-115">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="a4ac1-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="a4ac1-116">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a4ac1-116">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="a4ac1-117">Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="a4ac1-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="a4ac1-118">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="a4ac1-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#DIVIDE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#divide)]  
  
## <a name="see-also"></a><span data-ttu-id="a4ac1-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4ac1-119">See also</span></span>

- [<span data-ttu-id="a4ac1-120">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a4ac1-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
