---
title: REF (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: dfc91b60c68f55def8e7f81c2c5dd068c23f6e69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ref-entity-sql"></a><span data-ttu-id="a535a-102">REF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a535a-102">REF (Entity SQL)</span></span>
<span data-ttu-id="a535a-103">Restituisce un riferimento a un'istanza dell'entità.</span><span class="sxs-lookup"><span data-stu-id="a535a-103">Returns a reference to an entity instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a535a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a535a-104">Syntax</span></span>  
  
```  
REF( expression )   
```  
  
## <a name="arguments"></a><span data-ttu-id="a535a-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a535a-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="a535a-106">Qualsiasi espressione valida che produce un'istanza di un tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="a535a-106">Any valid expression that yields an instance of an entity type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a535a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a535a-107">Return Value</span></span>  
 <span data-ttu-id="a535a-108">Riferimento all'istanza dell'entità specificata.</span><span class="sxs-lookup"><span data-stu-id="a535a-108">A reference to the specified entity instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a535a-109">Note</span><span class="sxs-lookup"><span data-stu-id="a535a-109">Remarks</span></span>  
 <span data-ttu-id="a535a-110">Un riferimento all'entità è costituito dalla chiave di entità e dal nome di un set di entità.</span><span class="sxs-lookup"><span data-stu-id="a535a-110">An entity reference consists of the entity key and an entity set name.</span></span> <span data-ttu-id="a535a-111">Poiché set di entità diversi possono essere basati sullo stesso tipo di entità, una determinata chiave di entità può essere visualizzata in più set di entità.</span><span class="sxs-lookup"><span data-stu-id="a535a-111">Because different entity sets can be based on the same entity type, a particular entity key can appear in multiple entity sets.</span></span> <span data-ttu-id="a535a-112">Un riferimento all'entità è tuttavia sempre univoco.</span><span class="sxs-lookup"><span data-stu-id="a535a-112">However, an entity reference is always unique.</span></span> <span data-ttu-id="a535a-113">Se l'espressione di input rappresenta un'entità persistente, verrà restituito un riferimento a tale entità.</span><span class="sxs-lookup"><span data-stu-id="a535a-113">If the input expression represents a persisted entity, a reference to this entity will be returned.</span></span> <span data-ttu-id="a535a-114">Se l'espressione di input non è un'entità persistente, verrà restituito un riferimento Null.</span><span class="sxs-lookup"><span data-stu-id="a535a-114">If the input expression is not a persisted entity, a null reference will be returned.</span></span>  
  
 <span data-ttu-id="a535a-115">Quando viene usato l'operatore di estrazione delle proprietà (.), il riferimento viene automaticamente dereferenziato.</span><span class="sxs-lookup"><span data-stu-id="a535a-115">If the property extraction operator (.) is used to access a property of an entity, the reference is automatically dereferenced.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a535a-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="a535a-116">Example</span></span>  
 <span data-ttu-id="a535a-117">Nella query Entity SQL seguente viene usato l'operatore REF per restituire il riferimento per un argomento dell'entità di input.</span><span class="sxs-lookup"><span data-stu-id="a535a-117">The following Entity SQL query uses the REF operator to return the reference for an input entity argument.</span></span> <span data-ttu-id="a535a-118">Nella stessa query il riferimento viene dereferenziato in quanto viene usato l'operatore di estrazione delle proprietà (.) per accedere a una proprietà dell'entità Product.</span><span class="sxs-lookup"><span data-stu-id="a535a-118">The same query dereferences the reference because we are using a property extraction operation (.) to access a property of the Product entity.</span></span> <span data-ttu-id="a535a-119">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="a535a-119">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="a535a-120">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a535a-120">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="a535a-121">Attenersi alla procedura di [procedura: eseguire una Query che restituisce risultati di PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="a535a-121">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="a535a-122">Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="a535a-122">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#REF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref)]  
  
## <a name="see-also"></a><span data-ttu-id="a535a-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a535a-123">See Also</span></span>  
 [<span data-ttu-id="a535a-124">DEREF</span><span class="sxs-lookup"><span data-stu-id="a535a-124">DEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)  
 [<span data-ttu-id="a535a-125">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="a535a-125">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
 [<span data-ttu-id="a535a-126">CHIAVE</span><span class="sxs-lookup"><span data-stu-id="a535a-126">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
 [<span data-ttu-id="a535a-127">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a535a-127">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="a535a-128">Definizioni di tipo</span><span class="sxs-lookup"><span data-stu-id="a535a-128">Type Definitions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)
