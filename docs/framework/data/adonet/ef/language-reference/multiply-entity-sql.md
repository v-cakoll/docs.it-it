---
title: '* (Moltiplicazione) (Entity SQL)'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 508ce246-4e86-47dd-a605-4af4bebb9891
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: c7e2bcf15ab8d0cf24fdc6cb7e9db025784bd435
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="-multiply-entity-sql"></a><span data-ttu-id="a6e80-102">\* (moltiplicazione) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a6e80-102">\* (Multiply) (Entity SQL)</span></span>
<span data-ttu-id="a6e80-103">Moltiplica due espressioni.</span><span class="sxs-lookup"><span data-stu-id="a6e80-103">Multiplies two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6e80-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a6e80-104">Syntax</span></span>  
  
```  
expression * expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="a6e80-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a6e80-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="a6e80-106">Qualsiasi espressione valida con qualsiasi tipo di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="a6e80-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="a6e80-107">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="a6e80-107">Result Types</span></span>  
 <span data-ttu-id="a6e80-108">Tipo di dati ottenuto della promozione implicita del tipo dei due argomenti.</span><span class="sxs-lookup"><span data-stu-id="a6e80-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="a6e80-109">Per ulteriori informazioni sulla promozione implicita del tipo, vedere [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a6e80-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6e80-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="a6e80-110">Example</span></span>  
 <span data-ttu-id="a6e80-111">Nella query Entity SQL seguente viene usato l'operatore aritmetico \* per moltiplicare due numeri.</span><span class="sxs-lookup"><span data-stu-id="a6e80-111">The following Entity SQL query uses the \* arithmetic operator to multiply two numbers.</span></span> <span data-ttu-id="a6e80-112">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="a6e80-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="a6e80-113">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a6e80-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="a6e80-114">Seguire la procedura indicata in [Procedura: eseguire una query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="a6e80-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="a6e80-115">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="a6e80-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MULTIPLY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#multiply)]  
  
## <a name="see-also"></a><span data-ttu-id="a6e80-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6e80-116">See Also</span></span>  
 [<span data-ttu-id="a6e80-117">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a6e80-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
