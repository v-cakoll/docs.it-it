---
title: BETWEEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
ms.openlocfilehash: a0f5dd19c439861451b1e88c3ae35f9f265288fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150493"
---
# <a name="between-entity-sql"></a><span data-ttu-id="ec0e2-102">BETWEEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ec0e2-102">BETWEEN (Entity SQL)</span></span>
<span data-ttu-id="ec0e2-103">Determina se un'espressione restituisce un valore incluso in un intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="ec0e2-103">Determines whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="ec0e2-104">L'espressione [!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN ha la stessa funzionalità dell'espressione Transact-SQL BETWEEN.</span><span class="sxs-lookup"><span data-stu-id="ec0e2-104">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN expression has the same functionality as the Transact-SQL BETWEEN expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec0e2-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ec0e2-105">Syntax</span></span>  
  
```csharp  
expression [ NOT ] BETWEEN begin_expression AND end_expression
```  
  
## <a name="arguments"></a><span data-ttu-id="ec0e2-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="ec0e2-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ec0e2-107">Qualsiasi espressione valida da testare nell'intervallo definito da `begin_expression` e `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="ec0e2-107">Any valid expression to test for in the range defined by `begin_expression` and `end_expression`.</span></span> <span data-ttu-id="ec0e2-108">`expression` deve essere dello stesso tipo sia di `begin_expression` che di `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="ec0e2-108">`expression` must be the same type as both `begin_expression` and `end_expression`.</span></span>  
  
 `begin_expression`  
 <span data-ttu-id="ec0e2-109">Qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="ec0e2-109">Any valid expression.</span></span> <span data-ttu-id="ec0e2-110">`begin_expression` deve essere dello stesso tipo sia di `expression` che di `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="ec0e2-110">`begin_expression` must be the same type as both `expression` and `end_expression`.</span></span> <span data-ttu-id="ec0e2-111">`begin_expression` deve essere minore di `end_expression`; in caso contrario, il valore restituito sarà negativo.</span><span class="sxs-lookup"><span data-stu-id="ec0e2-111">`begin_expression` should be less than `end_expression`, else the return value will be negated.</span></span>  
  
 `end_expression`  
 <span data-ttu-id="ec0e2-112">Qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="ec0e2-112">Any valid expression.</span></span> <span data-ttu-id="ec0e2-113">`end_expression` deve essere dello stesso tipo sia di `expression` che di `begin_expression`.</span><span class="sxs-lookup"><span data-stu-id="ec0e2-113">`end_expression` must be the same type as both `expression` and `begin_expression`.</span></span>  
  
 <span data-ttu-id="ec0e2-114">NOT</span><span class="sxs-lookup"><span data-stu-id="ec0e2-114">NOT</span></span>  
 <span data-ttu-id="ec0e2-115">Specifica la negazione del risultato di BETWEEN.</span><span class="sxs-lookup"><span data-stu-id="ec0e2-115">Specifies that the result of BETWEEN be negated.</span></span>  
  
 <span data-ttu-id="ec0e2-116">AND</span><span class="sxs-lookup"><span data-stu-id="ec0e2-116">AND</span></span>  
 <span data-ttu-id="ec0e2-117">Segnaposto che indica che l'oggetto `expression` deve essere incluso nell'intervallo specificato da `begin_expression` e `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="ec0e2-117">Acts as a placeholder that indicates `expression` should be within the range indicated by `begin_expression` and `end_expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec0e2-118">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ec0e2-118">Return Value</span></span>  
 <span data-ttu-id="ec0e2-119">`true` se `expression` si trova tra l'intervallo indicato da `begin_expression` e `end_expression`; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="ec0e2-119">`true` if `expression` is between the range indicated by `begin_expression` and `end_expression`; otherwise, `false`.</span></span> <span data-ttu-id="ec0e2-120">Verrà restituito `null` se `expression` è `null` o se `begin_expression` o `end_expression` è `null`.</span><span class="sxs-lookup"><span data-stu-id="ec0e2-120">`null` will be returned if `expression` is `null` or if `begin_expression` or `end_expression` is `null`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec0e2-121">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ec0e2-121">Remarks</span></span>  
 <span data-ttu-id="ec0e2-122">Per specificare un intervallo esclusivo, utilizzare gli operatori maggiore di (>) e minore di (<) anziché BETWEEN.</span><span class="sxs-lookup"><span data-stu-id="ec0e2-122">To specify an exclusive range, use the greater than (>) and less than (<) operators instead of BETWEEN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec0e2-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="ec0e2-123">Example</span></span>  
 <span data-ttu-id="ec0e2-124">Nella query Entity SQL seguente viene usato l'operatore BETWEEN per determinare se un'espressione restituisce un valore incluso in un intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="ec0e2-124">The following Entity SQL query uses BETWEEN operator to determine whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="ec0e2-125">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="ec0e2-125">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ec0e2-126">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec0e2-126">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="ec0e2-127">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="ec0e2-127">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="ec0e2-128">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="ec0e2-128">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a><span data-ttu-id="ec0e2-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec0e2-129">See also</span></span>

- [<span data-ttu-id="ec0e2-130">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="ec0e2-130">Entity SQL Reference</span></span>](entity-sql-reference.md)
