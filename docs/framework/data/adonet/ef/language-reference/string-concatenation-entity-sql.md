---
title: + (Concatenazione di stringhe) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
ms.openlocfilehash: 9c078e193eeecd4d331c5e3c04c66dee2c4a1daa
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319318"
---
# <a name="-string-concatenation-entity-sql"></a><span data-ttu-id="39c6e-102">+ (concatenazione di stringhe) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="39c6e-102">+ (String Concatenation) (Entity SQL)</span></span>
<span data-ttu-id="39c6e-103">Concatena due stringhe.</span><span class="sxs-lookup"><span data-stu-id="39c6e-103">Concatenates two strings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39c6e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39c6e-104">Syntax</span></span>  
  
```sql  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="39c6e-105">argomenti</span><span class="sxs-lookup"><span data-stu-id="39c6e-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="39c6e-106">Qualsiasi espressione valida dei tipi di dati EDM.String.</span><span class="sxs-lookup"><span data-stu-id="39c6e-106">Any valid expression of the EDM.String data types.</span></span> <span data-ttu-id="39c6e-107">Entrambe le espressioni devono essere dello stesso tipo di dati oppure un'espressione deve poter essere convertita in modo implicito nel tipo di dati dell'altra espressione.</span><span class="sxs-lookup"><span data-stu-id="39c6e-107">Both expressions must be of the same data type, or one expression must be able to be implicitly converted to the data type of the other expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="39c6e-108">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="39c6e-108">Result Types</span></span>  
 <span data-ttu-id="39c6e-109">Tipo di dati ottenuto della promozione implicita del tipo dei due argomenti.</span><span class="sxs-lookup"><span data-stu-id="39c6e-109">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="39c6e-110">Per ulteriori informazioni sull'innalzamento di tipo implicito, vedere [System Type](type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="39c6e-110">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="39c6e-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="39c6e-111">Example</span></span>  
 <span data-ttu-id="39c6e-112">Nella query Entity SQL seguente viene usato l'operatore + per concatenare due stringhe.</span><span class="sxs-lookup"><span data-stu-id="39c6e-112">The following Entity SQL query uses the + operator to concatenates two strings.</span></span> <span data-ttu-id="39c6e-113">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="39c6e-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="39c6e-114">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="39c6e-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="39c6e-115">Attenersi alla procedura descritta in [procedura: eseguire una query che restituisce i risultati di PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="39c6e-115">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="39c6e-116">Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="39c6e-116">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#CONCAT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#concat)]  
  
## <a name="see-also"></a><span data-ttu-id="39c6e-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39c6e-117">See also</span></span>

- [<span data-ttu-id="39c6e-118">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="39c6e-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="39c6e-119">Tipi del modello concettuale (CSDL)</span><span class="sxs-lookup"><span data-stu-id="39c6e-119">Conceptual Model Types (CSDL)</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)
