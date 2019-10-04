---
title: '- Dividere (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: ef48c368-f3ed-4275-8ada-4e9649781262
ms.openlocfilehash: 79fdbebc648daac4f695387d52d2a915383f99ca
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833882"
---
# <a name="-divide-entity-sql"></a><span data-ttu-id="163fe-102">/ (divisione) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="163fe-102">/ (Divide) (Entity SQL)</span></span>
<span data-ttu-id="163fe-103">Divide un numero per un altro.</span><span class="sxs-lookup"><span data-stu-id="163fe-103">Divides one number by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="163fe-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="163fe-104">Syntax</span></span>  
  
```sql  
dividend / divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="163fe-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="163fe-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="163fe-106">Espressione numerica da dividere.</span><span class="sxs-lookup"><span data-stu-id="163fe-106">The numeric expression to divide.</span></span> <span data-ttu-id="163fe-107">`dividend` è qualsiasi espressione valida con qualsiasi tipo di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="163fe-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="163fe-108">Espressione numerica per la quale dividere il dividendo.</span><span class="sxs-lookup"><span data-stu-id="163fe-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="163fe-109">`divisor` è qualsiasi espressione valida con qualsiasi tipo di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="163fe-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="163fe-110">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="163fe-110">Result Types</span></span>  
 <span data-ttu-id="163fe-111">Tipo di dati ottenuto della promozione implicita del tipo dei due argomenti.</span><span class="sxs-lookup"><span data-stu-id="163fe-111">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="163fe-112">Per ulteriori informazioni sull'innalzamento di tipo implicito, vedere [System Type](type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="163fe-112">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="163fe-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="163fe-113">Example</span></span>  
 <span data-ttu-id="163fe-114">Nella query Entity SQL seguente viene usato l'operatore aritmetico/per dividere un numero per un altro.</span><span class="sxs-lookup"><span data-stu-id="163fe-114">The following Entity SQL query uses the / arithmetic operator to divide one number by another.</span></span> <span data-ttu-id="163fe-115">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="163fe-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="163fe-116">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="163fe-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="163fe-117">Seguire la procedura descritta in [How per: Eseguire una query che restituisce i risultati di StructuralType @ no__t-0.</span><span class="sxs-lookup"><span data-stu-id="163fe-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="163fe-118">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="163fe-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#DIVIDE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#divide)]  
  
## <a name="see-also"></a><span data-ttu-id="163fe-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="163fe-119">See also</span></span>

- [<span data-ttu-id="163fe-120">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="163fe-120">Entity SQL Reference</span></span>](entity-sql-reference.md)
