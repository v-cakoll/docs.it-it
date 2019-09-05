---
title: BETWEEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
ms.openlocfilehash: 41036e629837bd5861368df545bed9423eac5b23
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251289"
---
# <a name="between-entity-sql"></a><span data-ttu-id="1930e-102">BETWEEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="1930e-102">BETWEEN (Entity SQL)</span></span>
<span data-ttu-id="1930e-103">Determina se un'espressione restituisce un valore incluso in un intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="1930e-103">Determines whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="1930e-104">L' [!INCLUDE[esql](../../../../../../includes/esql-md.md)] espressione between ha la stessa funzionalità dell'espressione Transact-SQL between.</span><span class="sxs-lookup"><span data-stu-id="1930e-104">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN expression has the same functionality as the Transact-SQL BETWEEN expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1930e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1930e-105">Syntax</span></span>  
  
```  
expression [ NOT ] BETWEEN begin_expression AND end_expression    
```  
  
## <a name="arguments"></a><span data-ttu-id="1930e-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="1930e-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="1930e-107">Qualsiasi espressione valida da testare nell'intervallo definito da `begin_expression` e `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="1930e-107">Any valid expression to test for in the range defined by `begin_expression` and `end_expression`.</span></span> <span data-ttu-id="1930e-108">`expression` deve essere dello stesso tipo sia di `begin_expression` che di `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="1930e-108">`expression` must be the same type as both `begin_expression` and `end_expression`.</span></span>  
  
 `begin_expression`  
 <span data-ttu-id="1930e-109">Qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="1930e-109">Any valid expression.</span></span> <span data-ttu-id="1930e-110">`begin_expression` deve essere dello stesso tipo sia di `expression` che di `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="1930e-110">`begin_expression` must be the same type as both `expression` and `end_expression`.</span></span> <span data-ttu-id="1930e-111">`begin_expression` deve essere minore di `end_expression`; in caso contrario, il valore restituito sarà negativo.</span><span class="sxs-lookup"><span data-stu-id="1930e-111">`begin_expression` should be less than `end_expression`, else the return value will be negated.</span></span>  
  
 `end_expression`  
 <span data-ttu-id="1930e-112">Qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="1930e-112">Any valid expression.</span></span> <span data-ttu-id="1930e-113">`end_expression` deve essere dello stesso tipo sia di `expression` che di `begin_expression`.</span><span class="sxs-lookup"><span data-stu-id="1930e-113">`end_expression` must be the same type as both `expression` and `begin_expression`.</span></span>  
  
 <span data-ttu-id="1930e-114">NOT</span><span class="sxs-lookup"><span data-stu-id="1930e-114">NOT</span></span>  
 <span data-ttu-id="1930e-115">Specifica la negazione del risultato di BETWEEN.</span><span class="sxs-lookup"><span data-stu-id="1930e-115">Specifies that the result of BETWEEN be negated.</span></span>  
  
 <span data-ttu-id="1930e-116">AND</span><span class="sxs-lookup"><span data-stu-id="1930e-116">AND</span></span>  
 <span data-ttu-id="1930e-117">Segnaposto che indica che l'oggetto `expression` deve essere incluso nell'intervallo specificato da `begin_expression` e `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="1930e-117">Acts as a placeholder that indicates `expression` should be within the range indicated by `begin_expression` and `end_expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1930e-118">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1930e-118">Return Value</span></span>  
 <span data-ttu-id="1930e-119">`true` se `expression` si trova tra l'intervallo indicato da `begin_expression` e `end_expression`; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="1930e-119">`true` if `expression` is between the range indicated by `begin_expression` and `end_expression`; otherwise, `false`.</span></span> <span data-ttu-id="1930e-120">Verrà restituito `null` se `expression` è `null` o se `begin_expression` o `end_expression` è `null`.</span><span class="sxs-lookup"><span data-stu-id="1930e-120">`null` will be returned if `expression` is `null` or if `begin_expression` or `end_expression` is `null`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1930e-121">Note</span><span class="sxs-lookup"><span data-stu-id="1930e-121">Remarks</span></span>  
 <span data-ttu-id="1930e-122">Per specificare un intervallo esclusivo, utilizzare gli operatori maggiore di (>) e minore di (<) anziché tra.</span><span class="sxs-lookup"><span data-stu-id="1930e-122">To specify an exclusive range, use the greater than (>) and less than (<) operators instead of BETWEEN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1930e-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="1930e-123">Example</span></span>  
 <span data-ttu-id="1930e-124">Nella query Entity SQL seguente viene usato l'operatore BETWEEN per determinare se un'espressione restituisce un valore incluso in un intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="1930e-124">The following Entity SQL query uses BETWEEN operator to determine whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="1930e-125">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="1930e-125">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="1930e-126">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1930e-126">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="1930e-127">Attenersi alla procedura descritta [in procedura: Eseguire una query che restituisce i risultati](../how-to-execute-a-query-that-returns-structuraltype-results.md)di StructuralType.</span><span class="sxs-lookup"><span data-stu-id="1930e-127">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="1930e-128">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="1930e-128">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a><span data-ttu-id="1930e-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1930e-129">See also</span></span>

- [<span data-ttu-id="1930e-130">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="1930e-130">Entity SQL Reference</span></span>](entity-sql-reference.md)
