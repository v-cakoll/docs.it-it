---
title: '- Sottrarre (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: bc4327f9-09c0-438f-a008-927c5c478040
ms.openlocfilehash: fe9152100bddac86f3fb7fae1ab3c0b81ae58418
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319324"
---
# <a name="--subtract-entity-sql"></a><span data-ttu-id="650f9-102">- (sottrazione) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="650f9-102">- (Subtract) (Entity SQL)</span></span>
<span data-ttu-id="650f9-103">Esegue la sottrazione di due numeri.</span><span class="sxs-lookup"><span data-stu-id="650f9-103">Subtracts two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="650f9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="650f9-104">Syntax</span></span>  
  
```sql  
expression - expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="650f9-105">argomenti</span><span class="sxs-lookup"><span data-stu-id="650f9-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="650f9-106">Qualsiasi espressione valida con qualsiasi tipo di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="650f9-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="650f9-107">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="650f9-107">Result Types</span></span>  
 <span data-ttu-id="650f9-108">Tipo di dati ottenuto della promozione implicita del tipo dei due argomenti.</span><span class="sxs-lookup"><span data-stu-id="650f9-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="650f9-109">Per ulteriori informazioni sull'innalzamento di tipo implicito, vedere [System Type](type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="650f9-109">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="650f9-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="650f9-110">Example</span></span>  
 <span data-ttu-id="650f9-111">Nella query Entity SQL seguente viene usato l'operatore aritmetico - per sottrarre due numeri.</span><span class="sxs-lookup"><span data-stu-id="650f9-111">The following Entity SQL query uses the - arithmetic operator to subtract two numbers.</span></span> <span data-ttu-id="650f9-112">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="650f9-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="650f9-113">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="650f9-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="650f9-114">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="650f9-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="650f9-115">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="650f9-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#SUBTRACT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#subtract)]  
  
## <a name="see-also"></a><span data-ttu-id="650f9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="650f9-116">See also</span></span>

- [<span data-ttu-id="650f9-117">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="650f9-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
