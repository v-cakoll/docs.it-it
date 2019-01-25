---
title: + (String Concatenation) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
ms.openlocfilehash: e53bd0a2607deb67d45edc44e51cf4ad283b21c6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54633923"
---
# <a name="-string-concatenation-entity-sql"></a><span data-ttu-id="8870a-102">+ (concatenazione di stringhe) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8870a-102">+ (String Concatenation) (Entity SQL)</span></span>
<span data-ttu-id="8870a-103">Concatena due stringhe.</span><span class="sxs-lookup"><span data-stu-id="8870a-103">Concatenates two strings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8870a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8870a-104">Syntax</span></span>  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="8870a-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="8870a-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="8870a-106">Qualsiasi espressione valida dei tipi di dati EDM.String.</span><span class="sxs-lookup"><span data-stu-id="8870a-106">Any valid expression of the EDM.String data types.</span></span> <span data-ttu-id="8870a-107">Entrambe le espressioni devono essere dello stesso tipo di dati oppure un'espressione deve poter essere convertita in modo implicito nel tipo di dati dell'altra espressione.</span><span class="sxs-lookup"><span data-stu-id="8870a-107">Both expressions must be of the same data type, or one expression must be able to be implicitly converted to the data type of the other expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="8870a-108">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="8870a-108">Result Types</span></span>  
 <span data-ttu-id="8870a-109">Tipo di dati ottenuto della promozione implicita del tipo dei due argomenti.</span><span class="sxs-lookup"><span data-stu-id="8870a-109">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="8870a-110">Per altre informazioni sulla promozione implicita del tipo, vedere [sistema di tipi](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="8870a-110">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8870a-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="8870a-111">Example</span></span>  
 <span data-ttu-id="8870a-112">Nella query Entity SQL seguente viene usato l'operatore + per concatenare due stringhe.</span><span class="sxs-lookup"><span data-stu-id="8870a-112">The following Entity SQL query uses the + operator to concatenates two strings.</span></span> <span data-ttu-id="8870a-113">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="8870a-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="8870a-114">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8870a-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="8870a-115">Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="8870a-115">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="8870a-116">Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="8870a-116">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CONCAT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#concat)]  
  
## <a name="see-also"></a><span data-ttu-id="8870a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8870a-117">See also</span></span>
- [<span data-ttu-id="8870a-118">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="8870a-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="8870a-119">Tipi del modello concettuale (CSDL)</span><span class="sxs-lookup"><span data-stu-id="8870a-119">Conceptual Model Types (CSDL)</span></span>](https://msdn.microsoft.com/library/987b995f-e429-4569-9559-b4146744def4)
