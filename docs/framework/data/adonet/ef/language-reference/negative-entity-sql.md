---
title: '- Negativo (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
ms.openlocfilehash: effd537bcd53052830f2195e18ca959b49d87255
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249930"
---
# <a name="--negative-entity-sql"></a><span data-ttu-id="bbfa6-102">- (negativo) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="bbfa6-102">- (Negative) (Entity SQL)</span></span>
<span data-ttu-id="bbfa6-103">Restituisce il corrispondente negativo del valore di un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="bbfa6-103">Returns the negative of the value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbfa6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bbfa6-104">Syntax</span></span>  
  
```  
- expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="bbfa6-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="bbfa6-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="bbfa6-106">Qualsiasi espressione valida con qualsiasi tipo di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="bbfa6-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="bbfa6-107">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="bbfa6-107">Result Types</span></span>  
 <span data-ttu-id="bbfa6-108">Tipo di dati di `expression`.</span><span class="sxs-lookup"><span data-stu-id="bbfa6-108">The data type of `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbfa6-109">Note</span><span class="sxs-lookup"><span data-stu-id="bbfa6-109">Remarks</span></span>  
 <span data-ttu-id="bbfa6-110">Se `expression` è un tipo senza segno, il tipo di risultato sarà il tipo con segno più strettamente correlato al tipo di `expression`.</span><span class="sxs-lookup"><span data-stu-id="bbfa6-110">If `expression` is an unsigned type, the result type will be the signed type that most closely relates to the type of `expression`.</span></span> <span data-ttu-id="bbfa6-111">Se, ad esempio, `expression` è di tipo Byte, verrà restituito un valore di tipo Int16.</span><span class="sxs-lookup"><span data-stu-id="bbfa6-111">For example, if `expression` is of type Byte, a value of type Int16 will be returned.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbfa6-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="bbfa6-112">Example</span></span>  
 <span data-ttu-id="bbfa6-113">Nella query Entity SQL seguente viene usato l'operatore aritmetico - per restituire il corrispondente negativo del valore di un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="bbfa6-113">The following Entity SQL query uses the - arithmetic operator to return the negative of the value of a numeric expression.</span></span> <span data-ttu-id="bbfa6-114">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="bbfa6-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="bbfa6-115">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bbfa6-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="bbfa6-116">Attenersi alla procedura descritta [in procedura: Eseguire una query che restituisce i risultati](../how-to-execute-a-query-that-returns-structuraltype-results.md)di StructuralType.</span><span class="sxs-lookup"><span data-stu-id="bbfa6-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="bbfa6-117">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="bbfa6-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NEGATIVE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#negative)]  
  
## <a name="see-also"></a><span data-ttu-id="bbfa6-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbfa6-118">See also</span></span>

- [<span data-ttu-id="bbfa6-119">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="bbfa6-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
