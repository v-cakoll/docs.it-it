---
title: + (Concatenazione di stringhe) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
ms.openlocfilehash: 1826d1267f0ee5ad8320cf1d1ab36f87adf765a5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="-string-concatenation-entity-sql"></a><span data-ttu-id="a5de7-102">+ (concatenazione di stringhe) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a5de7-102">+ (String Concatenation) (Entity SQL)</span></span>
<span data-ttu-id="a5de7-103">Concatena due stringhe.</span><span class="sxs-lookup"><span data-stu-id="a5de7-103">Concatenates two strings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5de7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a5de7-104">Syntax</span></span>  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="a5de7-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a5de7-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="a5de7-106">Qualsiasi espressione valida dei tipi di dati EDM.String.</span><span class="sxs-lookup"><span data-stu-id="a5de7-106">Any valid expression of the EDM.String data types.</span></span> <span data-ttu-id="a5de7-107">Entrambe le espressioni devono essere dello stesso tipo di dati oppure un'espressione deve poter essere convertita in modo implicito nel tipo di dati dell'altra espressione.</span><span class="sxs-lookup"><span data-stu-id="a5de7-107">Both expressions must be of the same data type, or one expression must be able to be implicitly converted to the data type of the other expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="a5de7-108">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="a5de7-108">Result Types</span></span>  
 <span data-ttu-id="a5de7-109">Tipo di dati ottenuto della promozione implicita del tipo dei due argomenti.</span><span class="sxs-lookup"><span data-stu-id="a5de7-109">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="a5de7-110">Per ulteriori informazioni sulla promozione implicita del tipo, vedere [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a5de7-110">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5de7-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="a5de7-111">Example</span></span>  
 <span data-ttu-id="a5de7-112">Nella query Entity SQL seguente viene usato l'operatore + per concatenare due stringhe.</span><span class="sxs-lookup"><span data-stu-id="a5de7-112">The following Entity SQL query uses the + operator to concatenates two strings.</span></span> <span data-ttu-id="a5de7-113">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="a5de7-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="a5de7-114">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a5de7-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="a5de7-115">Attenersi alla procedura di [procedura: eseguire una Query che restituisce risultati di PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="a5de7-115">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="a5de7-116">Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="a5de7-116">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CONCAT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#concat)]  
  
## <a name="see-also"></a><span data-ttu-id="a5de7-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5de7-117">See Also</span></span>  
 [<span data-ttu-id="a5de7-118">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a5de7-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="a5de7-119">Tipi di modello concettuale (CSDL)</span><span class="sxs-lookup"><span data-stu-id="a5de7-119">Conceptual Model Types (CSDL)</span></span>](http://msdn.microsoft.com/library/987b995f-e429-4569-9559-b4146744def4)
