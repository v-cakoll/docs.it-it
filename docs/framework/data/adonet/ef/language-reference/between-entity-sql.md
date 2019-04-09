---
title: BETWEEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
ms.openlocfilehash: 2c411fd7fcac9d98323d5fcfb1874f98bc664991
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225261"
---
# <a name="between-entity-sql"></a><span data-ttu-id="7b021-102">BETWEEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="7b021-102">BETWEEN (Entity SQL)</span></span>
<span data-ttu-id="7b021-103">Determina se un'espressione restituisce un valore incluso in un intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="7b021-103">Determines whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="7b021-104">Il [!INCLUDE[esql](../../../../../../includes/esql-md.md)] espressione BETWEEN ha la stessa funzionalità come l'espressione BETWEEN Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="7b021-104">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN expression has the same functionality as the Transact-SQL BETWEEN expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b021-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7b021-105">Syntax</span></span>  
  
```  
expression [ NOT ] BETWEEN begin_expression AND end_expression    
```  
  
## <a name="arguments"></a><span data-ttu-id="7b021-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="7b021-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="7b021-107">Qualsiasi espressione valida da testare nell'intervallo definito da `begin_expression` e `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="7b021-107">Any valid expression to test for in the range defined by `begin_expression` and `end_expression`.</span></span> `expression` <span data-ttu-id="7b021-108">deve essere dello stesso tipo di `begin_expression` e `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="7b021-108">must be the same type as both `begin_expression` and `end_expression`.</span></span>  
  
 `begin_expression`  
 <span data-ttu-id="7b021-109">Qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="7b021-109">Any valid expression.</span></span> `begin_expression` <span data-ttu-id="7b021-110">deve essere dello stesso tipo di `expression` e `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="7b021-110">must be the same type as both `expression` and `end_expression`.</span></span> `begin_expression` <span data-ttu-id="7b021-111">deve essere minore di `end_expression`, altrimenti il valore restituito sarà negativo.</span><span class="sxs-lookup"><span data-stu-id="7b021-111">should be less than `end_expression`, else the return value will be negated.</span></span>  
  
 `end_expression`  
 <span data-ttu-id="7b021-112">Qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="7b021-112">Any valid expression.</span></span> `end_expression` <span data-ttu-id="7b021-113">deve essere dello stesso tipo di `expression` e `begin_expression`.</span><span class="sxs-lookup"><span data-stu-id="7b021-113">must be the same type as both `expression` and `begin_expression`.</span></span>  
  
 <span data-ttu-id="7b021-114">NOT</span><span class="sxs-lookup"><span data-stu-id="7b021-114">NOT</span></span>  
 <span data-ttu-id="7b021-115">Specifica la negazione del risultato di BETWEEN.</span><span class="sxs-lookup"><span data-stu-id="7b021-115">Specifies that the result of BETWEEN be negated.</span></span>  
  
 <span data-ttu-id="7b021-116">AND</span><span class="sxs-lookup"><span data-stu-id="7b021-116">AND</span></span>  
 <span data-ttu-id="7b021-117">Segnaposto che indica che l'oggetto `expression` deve essere incluso nell'intervallo specificato da `begin_expression` e `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="7b021-117">Acts as a placeholder that indicates `expression` should be within the range indicated by `begin_expression` and `end_expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b021-118">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7b021-118">Return Value</span></span>  
 `true` <span data-ttu-id="7b021-119">Se `expression` è incluso nell'intervallo indicato dal `begin_expression` e `end_expression`; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="7b021-119">if `expression` is between the range indicated by `begin_expression` and `end_expression`; otherwise, `false`.</span></span> `null` <span data-ttu-id="7b021-120">Se viene restituito `expression` viene `null` o se `begin_expression` oppure `end_expression` è `null`.</span><span class="sxs-lookup"><span data-stu-id="7b021-120">will be returned if `expression` is `null` or if `begin_expression` or `end_expression` is `null`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b021-121">Note</span><span class="sxs-lookup"><span data-stu-id="7b021-121">Remarks</span></span>  
 <span data-ttu-id="7b021-122">Per specificare un intervallo esclusivo, utilizzare la maggiore (>) e minore di (<) operatori anziché BETWEEN.</span><span class="sxs-lookup"><span data-stu-id="7b021-122">To specify an exclusive range, use the greater than (>) and less than (<) operators instead of BETWEEN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b021-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="7b021-123">Example</span></span>  
 <span data-ttu-id="7b021-124">Nella query Entity SQL seguente viene usato l'operatore BETWEEN per determinare se un'espressione restituisce un valore incluso in un intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="7b021-124">The following Entity SQL query uses BETWEEN operator to determine whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="7b021-125">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="7b021-125">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="7b021-126">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b021-126">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="7b021-127">Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="7b021-127">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="7b021-128">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="7b021-128">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a><span data-ttu-id="7b021-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b021-129">See also</span></span>

- [<span data-ttu-id="7b021-130">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="7b021-130">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
