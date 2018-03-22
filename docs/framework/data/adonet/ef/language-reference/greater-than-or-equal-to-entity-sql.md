---
title: '&gt;= (maggiore o uguale a) (Entity SQL)'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70780ac4-0123-4da8-b731-8af856daffe3
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: b176e1efdc17b58083234d0437033bd43775f604
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="gt-greater-than-or-equal-to-entity-sql"></a><span data-ttu-id="f0ec8-102">&gt;= (maggiore o uguale a) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f0ec8-102">&gt;= (Greater Than or Equal To) (Entity SQL)</span></span>
<span data-ttu-id="f0ec8-103">Consente di confrontare due espressioni per determinare se l'espressione a sinistra ha un valore maggiore o uguale a quella a destra.</span><span class="sxs-lookup"><span data-stu-id="f0ec8-103">Compares two expressions to determine whether the left expression has a value greater than or equal to the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0ec8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f0ec8-104">Syntax</span></span>  
  
```  
expression >= expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="f0ec8-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="f0ec8-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="f0ec8-106">Qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="f0ec8-106">Any valid expression.</span></span> <span data-ttu-id="f0ec8-107">Entrambe le espressioni devono contenere tipi di dati convertibili in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="f0ec8-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="f0ec8-108">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="f0ec8-108">Result Types</span></span>  
 <span data-ttu-id="f0ec8-109">`true` se l'espressione a sinistra ha un valore maggiore o uguale a quella a destra; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="f0ec8-109">`true` if the left expression has a value greater than or equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0ec8-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="f0ec8-110">Example</span></span>  
 <span data-ttu-id="f0ec8-111">Nella query Entity SQL seguente viene usato l'operatore di confronto >= per confrontare due espressioni e determinare se l'espressione a sinistra ha un valore maggiore o uguale a quella a destra.</span><span class="sxs-lookup"><span data-stu-id="f0ec8-111">The following Entity SQL query uses >= comparison operator to compare two expressions to determine whether the left expression has a value greater than or equal to the right expression.</span></span> <span data-ttu-id="f0ec8-112">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="f0ec8-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="f0ec8-113">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f0ec8-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="f0ec8-114">Seguire la procedura indicata in [Procedura: eseguire una query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="f0ec8-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="f0ec8-115">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="f0ec8-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER_OR_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater_or_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="f0ec8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0ec8-116">See Also</span></span>  
 [<span data-ttu-id="f0ec8-117">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f0ec8-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
