---
title: '- Negativo (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
ms.openlocfilehash: 7716b9115587a873531be9c14b7da93c7a148ed8
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319529"
---
# <a name="--negative-entity-sql"></a><span data-ttu-id="2aa88-102">- (negativo) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2aa88-102">- (Negative) (Entity SQL)</span></span>
<span data-ttu-id="2aa88-103">Restituisce il corrispondente negativo del valore di un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="2aa88-103">Returns the negative of the value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2aa88-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2aa88-104">Syntax</span></span>  
  
```sql  
- expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="2aa88-105">argomenti</span><span class="sxs-lookup"><span data-stu-id="2aa88-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="2aa88-106">Qualsiasi espressione valida con qualsiasi tipo di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="2aa88-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="2aa88-107">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="2aa88-107">Result Types</span></span>  
 <span data-ttu-id="2aa88-108">Tipo di dati di `expression`.</span><span class="sxs-lookup"><span data-stu-id="2aa88-108">The data type of `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2aa88-109">Note</span><span class="sxs-lookup"><span data-stu-id="2aa88-109">Remarks</span></span>  
 <span data-ttu-id="2aa88-110">Se `expression` è un tipo senza segno, il tipo di risultato sarà il tipo con segno più strettamente correlato al tipo di `expression`.</span><span class="sxs-lookup"><span data-stu-id="2aa88-110">If `expression` is an unsigned type, the result type will be the signed type that most closely relates to the type of `expression`.</span></span> <span data-ttu-id="2aa88-111">Se, ad esempio, `expression` è di tipo Byte, verrà restituito un valore di tipo Int16.</span><span class="sxs-lookup"><span data-stu-id="2aa88-111">For example, if `expression` is of type Byte, a value of type Int16 will be returned.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2aa88-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="2aa88-112">Example</span></span>  
 <span data-ttu-id="2aa88-113">Nella query Entity SQL seguente viene usato l'operatore aritmetico - per restituire il corrispondente negativo del valore di un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="2aa88-113">The following Entity SQL query uses the - arithmetic operator to return the negative of the value of a numeric expression.</span></span> <span data-ttu-id="2aa88-114">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="2aa88-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="2aa88-115">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2aa88-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="2aa88-116">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="2aa88-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="2aa88-117">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="2aa88-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NEGATIVE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#negative)]  
  
## <a name="see-also"></a><span data-ttu-id="2aa88-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2aa88-118">See also</span></span>

- [<span data-ttu-id="2aa88-119">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="2aa88-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
