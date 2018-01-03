---
title: COLLECTION (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: c850fe215c692f204c6762d82a3d37b29c556a7c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="collection-entity-sql"></a><span data-ttu-id="f8113-102">COLLECTION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f8113-102">COLLECTION (Entity SQL)</span></span>
<span data-ttu-id="f8113-103">La parola chiave COLLECTION viene usata solo nella definizione di una funzione inline.</span><span class="sxs-lookup"><span data-stu-id="f8113-103">The COLLECTION keyword is only used in the definition of an inline function.</span></span> <span data-ttu-id="f8113-104">Le funzioni di raccolta sono funzioni che operano su una raccolta di valori e producono un output scalare.</span><span class="sxs-lookup"><span data-stu-id="f8113-104">Collection functions are functions that operate on a collection of values and produce a scalar output.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8113-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f8113-105">Syntax</span></span>  
  
```  
COLLECTION(type_definition)   
```  
  
## <a name="arguments"></a><span data-ttu-id="f8113-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="f8113-106">Arguments</span></span>  
 `type_definition`  
 <span data-ttu-id="f8113-107">Espressione che restituisce una raccolta di tipi supportati, righe o riferimenti.</span><span class="sxs-lookup"><span data-stu-id="f8113-107">An expression that returns a collection of supported types, rows, or references.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8113-108">Note</span><span class="sxs-lookup"><span data-stu-id="f8113-108">Remarks</span></span>  
 <span data-ttu-id="f8113-109">Per altre informazioni sulla parola chiave COLLECTION, vedere [Type Definitions](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f8113-109">For more information about the COLLECTION keyword, see [Type Definitions](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8113-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="f8113-110">Example</span></span>  
 <span data-ttu-id="f8113-111">Nell'esempio seguente viene mostrato come usare la parola chiave COLLECTION per dichiarare una raccolta di numeri decimali come argomento di una funzione inline della query.</span><span class="sxs-lookup"><span data-stu-id="f8113-111">The following sample shows how to use the COLLECTION keyword to declare a collection of decimals as an argument for an inline query function.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]  
  
## <a name="see-also"></a><span data-ttu-id="f8113-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8113-112">See Also</span></span>  
 [<span data-ttu-id="f8113-113">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f8113-113">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
