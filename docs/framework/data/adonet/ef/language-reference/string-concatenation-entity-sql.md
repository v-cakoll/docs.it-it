---
title: + (Concatenazione di stringhe) (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 6019f6025b3a3996c9b86a6c9e61a3dd345c1b12
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="-string-concatenation-entity-sql"></a><span data-ttu-id="361d3-102">+ (concatenazione di stringhe) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="361d3-102">+ (String Concatenation) (Entity SQL)</span></span>
<span data-ttu-id="361d3-103">Concatena due stringhe.</span><span class="sxs-lookup"><span data-stu-id="361d3-103">Concatenates two strings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="361d3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="361d3-104">Syntax</span></span>  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="361d3-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="361d3-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="361d3-106">Qualsiasi espressione valida dei tipi di dati EDM.String.</span><span class="sxs-lookup"><span data-stu-id="361d3-106">Any valid expression of the EDM.String data types.</span></span> <span data-ttu-id="361d3-107">Entrambe le espressioni devono essere dello stesso tipo di dati oppure un'espressione deve poter essere convertita in modo implicito nel tipo di dati dell'altra espressione.</span><span class="sxs-lookup"><span data-stu-id="361d3-107">Both expressions must be of the same data type, or one expression must be able to be implicitly converted to the data type of the other expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="361d3-108">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="361d3-108">Result Types</span></span>  
 <span data-ttu-id="361d3-109">Tipo di dati ottenuto della promozione implicita del tipo dei due argomenti.</span><span class="sxs-lookup"><span data-stu-id="361d3-109">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="361d3-110">Per ulteriori informazioni sulla promozione implicita del tipo, vedere [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="361d3-110">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="361d3-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="361d3-111">Example</span></span>  
 <span data-ttu-id="361d3-112">Nella query Entity SQL seguente viene usato l'operatore + per concatenare due stringhe.</span><span class="sxs-lookup"><span data-stu-id="361d3-112">The following Entity SQL query uses the + operator to concatenates two strings.</span></span> <span data-ttu-id="361d3-113">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="361d3-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="361d3-114">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="361d3-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="361d3-115">Attenersi alla procedura di [procedura: eseguire una Query che restituisce risultati di PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="361d3-115">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="361d3-116">Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="361d3-116">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CONCAT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#concat)]  
  
## <a name="see-also"></a><span data-ttu-id="361d3-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="361d3-117">See Also</span></span>  
 [<span data-ttu-id="361d3-118">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="361d3-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="361d3-119">Tipi di modello concettuale (CSDL)</span><span class="sxs-lookup"><span data-stu-id="361d3-119">Conceptual Model Types (CSDL)</span></span>](http://msdn.microsoft.com/en-us/987b995f-e429-4569-9559-b4146744def4)
