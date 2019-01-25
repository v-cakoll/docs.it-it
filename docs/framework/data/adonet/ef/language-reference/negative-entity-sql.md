---
title: '- (Negative) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
ms.openlocfilehash: f33b672ecd635234b8a8859651d117aabdaf14d5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745853"
---
# <a name="--negative-entity-sql"></a><span data-ttu-id="be6fb-102">- (negativo) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="be6fb-102">- (Negative) (Entity SQL)</span></span>
<span data-ttu-id="be6fb-103">Restituisce il corrispondente negativo del valore di un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="be6fb-103">Returns the negative of the value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be6fb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="be6fb-104">Syntax</span></span>  
  
```  
- expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="be6fb-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="be6fb-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="be6fb-106">Qualsiasi espressione valida con qualsiasi tipo di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="be6fb-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="be6fb-107">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="be6fb-107">Result Types</span></span>  
 <span data-ttu-id="be6fb-108">Tipo di dati di `expression`.</span><span class="sxs-lookup"><span data-stu-id="be6fb-108">The data type of `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be6fb-109">Note</span><span class="sxs-lookup"><span data-stu-id="be6fb-109">Remarks</span></span>  
 <span data-ttu-id="be6fb-110">Se `expression` è un tipo senza segno, il tipo di risultato sarà il tipo con segno più strettamente correlato al tipo di `expression`.</span><span class="sxs-lookup"><span data-stu-id="be6fb-110">If `expression` is an unsigned type, the result type will be the signed type that most closely relates to the type of `expression`.</span></span> <span data-ttu-id="be6fb-111">Se, ad esempio, `expression` è di tipo Byte, verrà restituito un valore di tipo Int16.</span><span class="sxs-lookup"><span data-stu-id="be6fb-111">For example, if `expression` is of type Byte, a value of type Int16 will be returned.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be6fb-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="be6fb-112">Example</span></span>  
 <span data-ttu-id="be6fb-113">Nella query Entity SQL seguente viene usato l'operatore aritmetico - per restituire il corrispondente negativo del valore di un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="be6fb-113">The following Entity SQL query uses the - arithmetic operator to return the negative of the value of a numeric expression.</span></span> <span data-ttu-id="be6fb-114">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="be6fb-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="be6fb-115">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="be6fb-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="be6fb-116">Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="be6fb-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="be6fb-117">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="be6fb-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NEGATIVE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#negative)]  
  
## <a name="see-also"></a><span data-ttu-id="be6fb-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be6fb-118">See also</span></span>
- [<span data-ttu-id="be6fb-119">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="be6fb-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
