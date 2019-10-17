---
title: '* Moltiplicare (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 508ce246-4e86-47dd-a605-4af4bebb9891
ms.openlocfilehash: 7006f5143e8cc18156f748ae7664f3787c9ff5c9
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319617"
---
# <a name="-multiply-entity-sql"></a><span data-ttu-id="d7eac-102">\* (moltiplicazione) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d7eac-102">\* (Multiply) (Entity SQL)</span></span>
<span data-ttu-id="d7eac-103">Moltiplica due espressioni.</span><span class="sxs-lookup"><span data-stu-id="d7eac-103">Multiplies two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7eac-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d7eac-104">Syntax</span></span>  
  
```sql  
expression * expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="d7eac-105">argomenti</span><span class="sxs-lookup"><span data-stu-id="d7eac-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="d7eac-106">Qualsiasi espressione valida con qualsiasi tipo di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="d7eac-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="d7eac-107">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="d7eac-107">Result Types</span></span>  
 <span data-ttu-id="d7eac-108">Tipo di dati ottenuto della promozione implicita del tipo dei due argomenti.</span><span class="sxs-lookup"><span data-stu-id="d7eac-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="d7eac-109">Per ulteriori informazioni sull'innalzamento di tipo implicito, vedere [System Type](type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="d7eac-109">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7eac-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="d7eac-110">Example</span></span>  
 <span data-ttu-id="d7eac-111">Nella query Entity SQL seguente viene usato l'operatore aritmetico \* per moltiplicare due numeri.</span><span class="sxs-lookup"><span data-stu-id="d7eac-111">The following Entity SQL query uses the \* arithmetic operator to multiply two numbers.</span></span> <span data-ttu-id="d7eac-112">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="d7eac-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d7eac-113">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7eac-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="d7eac-114">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="d7eac-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="d7eac-115">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="d7eac-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#MULTIPLY](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#multiply)]  
  
## <a name="see-also"></a><span data-ttu-id="d7eac-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7eac-116">See also</span></span>

- [<span data-ttu-id="d7eac-117">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d7eac-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
