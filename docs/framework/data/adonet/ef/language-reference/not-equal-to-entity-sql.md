---
title: '!= (diverso da) (Entity SQL)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b4a02ad-ddfc-4c42-8dfa-676234461312
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a2187e317229961b0929f1415cd40f6f65f5c593
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="-not-equal-to-entity-sql"></a><span data-ttu-id="f4c8f-102">!= (diverso da) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f4c8f-102">!= (Not Equal To) (Entity SQL)</span></span>
<span data-ttu-id="f4c8f-103">Consente di confrontare due espressioni per determinare se l'espressione a sinistra è diversa da quella a destra.</span><span class="sxs-lookup"><span data-stu-id="f4c8f-103">Compares two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="f4c8f-104">L'operatore !=(diverso da) equivale dal punto di vista funzionale all'operatore <>.</span><span class="sxs-lookup"><span data-stu-id="f4c8f-104">The != (Not Equal To) operator is functionally equivalent to the <> operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4c8f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f4c8f-105">Syntax</span></span>  
  
```  
expression != expression  
or  
expression <> expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="f4c8f-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="f4c8f-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="f4c8f-107">Qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="f4c8f-107">Any valid expression.</span></span> <span data-ttu-id="f4c8f-108">Entrambe le espressioni devono contenere tipi di dati convertibili in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="f4c8f-108">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="f4c8f-109">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="f4c8f-109">Result Types</span></span>  
 <span data-ttu-id="f4c8f-110">`true` se l'espressione a sinistra è diversa da quella a destra; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="f4c8f-110">`true` if the left expression is not equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4c8f-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="f4c8f-111">Example</span></span>  
 <span data-ttu-id="f4c8f-112">Nella query Entity SQL seguente viene usato l'operatore != per confrontare due espressioni e determinare se l'espressione a sinistra è diversa da quella a destra.</span><span class="sxs-lookup"><span data-stu-id="f4c8f-112">The following Entity SQL query uses the != operator to compare two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="f4c8f-113">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="f4c8f-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="f4c8f-114">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4c8f-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="f4c8f-115">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="f4c8f-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="f4c8f-116">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="f4c8f-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="f4c8f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4c8f-117">See Also</span></span>  
 [<span data-ttu-id="f4c8f-118">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f4c8f-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
