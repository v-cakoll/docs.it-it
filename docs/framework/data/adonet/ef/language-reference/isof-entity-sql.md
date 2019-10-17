---
title: ISOF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b2b0d34-d0a7-4bcd-baf2-58aa8456d00b
ms.openlocfilehash: c4c4cbf74cb17cf43e79c42ff42d1e68122fd534
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319710"
---
# <a name="isof-entity-sql"></a><span data-ttu-id="87370-102">ISOF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="87370-102">ISOF (Entity SQL)</span></span>
<span data-ttu-id="87370-103">Determina se il tipo di un'espressione è del tipo specificato o di uno dei sottotipi.</span><span class="sxs-lookup"><span data-stu-id="87370-103">Determines whether the type of an expression is of the specified type or one of its subtypes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87370-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="87370-104">Syntax</span></span>  
  
```sql  
expression IS [ NOT ] OF ( [ ONLY ] type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="87370-105">argomenti</span><span class="sxs-lookup"><span data-stu-id="87370-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="87370-106">Qualsiasi espressione di query valida di cui determinare il tipo.</span><span class="sxs-lookup"><span data-stu-id="87370-106">Any valid query expression to determine the type of.</span></span>  
  
 <span data-ttu-id="87370-107">NOT</span><span class="sxs-lookup"><span data-stu-id="87370-107">NOT</span></span>  
 <span data-ttu-id="87370-108">Nega il risultato EDM.Boolean di IS OF.</span><span class="sxs-lookup"><span data-stu-id="87370-108">Negates the EDM.Boolean result of IS OF.</span></span>  
  
 <span data-ttu-id="87370-109">ONLY</span><span class="sxs-lookup"><span data-stu-id="87370-109">ONLY</span></span>  
 <span data-ttu-id="87370-110">Specifica che IS OF restituisce `true` solo se `expression` è di tipo `type` e non di uno dei sottotipi.</span><span class="sxs-lookup"><span data-stu-id="87370-110">Specifies that IS OF returns `true` only if `expression` is of type `type` and not any of one its subtypes.</span></span>  
  
 `type`  
 <span data-ttu-id="87370-111">Tipo rispetto al quale testare `expression`.</span><span class="sxs-lookup"><span data-stu-id="87370-111">The type to test `expression` against.</span></span> <span data-ttu-id="87370-112">Il tipo deve essere qualificato dallo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="87370-112">The type must be namespace-qualified.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87370-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="87370-113">Return Value</span></span>  
 <span data-ttu-id="87370-114">`true` se `expression` è di tipo T e T è un tipo di base o un tipo derivato di `type`; null se `expression` è null in fase di runtime; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="87370-114">`true` if `expression` is of type T and T is either a base type, or a derived type of `type`; null if `expression` is null at runtime; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87370-115">Note</span><span class="sxs-lookup"><span data-stu-id="87370-115">Remarks</span></span>  
 <span data-ttu-id="87370-116">Le espressioni `expression IS NOT OF (type)` e `expression IS NOT OF (ONLY type)` sono sintatticamente equivalenti rispettivamente a `NOT (expression IS OF (type))` e `NOT (expression IS OF (ONLY type))`.</span><span class="sxs-lookup"><span data-stu-id="87370-116">The expressions `expression IS NOT OF (type)` and `expression IS NOT OF (ONLY type)` are syntactically equivalent to `NOT (expression IS OF (type))` and `NOT (expression IS OF (ONLY type))`, respectively.</span></span>  
  
 <span data-ttu-id="87370-117">Nella tabella seguente viene illustrato il comportamento dell'operatore `IS OF` su alcuni modelli tipici e specifici.</span><span class="sxs-lookup"><span data-stu-id="87370-117">The following table shows the behavior of `IS OF` operator over some typical- and corner patterns.</span></span> <span data-ttu-id="87370-118">Tutte le eccezioni vengono generate sul lato client prima che il provider venga richiamato:</span><span class="sxs-lookup"><span data-stu-id="87370-118">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="87370-119">Criterio</span><span class="sxs-lookup"><span data-stu-id="87370-119">Pattern</span></span>|<span data-ttu-id="87370-120">Comportamento</span><span class="sxs-lookup"><span data-stu-id="87370-120">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="87370-121">null IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="87370-121">null IS OF (EntityType)</span></span>|<span data-ttu-id="87370-122">Genera un'eccezione</span><span class="sxs-lookup"><span data-stu-id="87370-122">Throws</span></span>|  
|<span data-ttu-id="87370-123">null IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="87370-123">null IS OF (ComplexType)</span></span>|<span data-ttu-id="87370-124">Genera un'eccezione</span><span class="sxs-lookup"><span data-stu-id="87370-124">Throws</span></span>|  
|<span data-ttu-id="87370-125">null IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="87370-125">null IS OF (RowType)</span></span>|<span data-ttu-id="87370-126">Genera un'eccezione</span><span class="sxs-lookup"><span data-stu-id="87370-126">Throws</span></span>|  
|<span data-ttu-id="87370-127">TREAT (null AS EntityType) IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="87370-127">TREAT (null AS EntityType) IS OF (EntityType)</span></span>|<span data-ttu-id="87370-128">Restituisce DBNull</span><span class="sxs-lookup"><span data-stu-id="87370-128">Returns DBNull</span></span>|  
|<span data-ttu-id="87370-129">TREAT (null AS ComplexType) IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="87370-129">TREAT (null AS ComplexType) IS OF (ComplexType)</span></span>|<span data-ttu-id="87370-130">Genera un'eccezione</span><span class="sxs-lookup"><span data-stu-id="87370-130">Throws</span></span>|  
|<span data-ttu-id="87370-131">TREAT (null AS RowType) IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="87370-131">TREAT (null AS RowType) IS OF (RowType)</span></span>|<span data-ttu-id="87370-132">Genera un'eccezione</span><span class="sxs-lookup"><span data-stu-id="87370-132">Throws</span></span>|  
|<span data-ttu-id="87370-133">EntityType IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="87370-133">EntityType IS OF (EntityType)</span></span>|<span data-ttu-id="87370-134">Restituisce true/false</span><span class="sxs-lookup"><span data-stu-id="87370-134">Returns true/false</span></span>|  
|<span data-ttu-id="87370-135">ComplexType IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="87370-135">ComplexType IS OF (ComplexType)</span></span>|<span data-ttu-id="87370-136">Genera un'eccezione</span><span class="sxs-lookup"><span data-stu-id="87370-136">Throws</span></span>|  
|<span data-ttu-id="87370-137">RowType IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="87370-137">RowType IS OF (RowType)</span></span>|<span data-ttu-id="87370-138">Genera un'eccezione</span><span class="sxs-lookup"><span data-stu-id="87370-138">Throws</span></span>|  
  
## <a name="example"></a><span data-ttu-id="87370-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="87370-139">Example</span></span>  
 <span data-ttu-id="87370-140">Nella query di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguente viene usato l'operatore IS OF per determinare il tipo di un'espressione di query, quindi viene usato l'operatore TREAT per convertire un oggetto del tipo Course in una raccolta di oggetti di tipo OnsiteCourse.</span><span class="sxs-lookup"><span data-stu-id="87370-140">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS OF operator to determine the type of a query expression, and then uses the TREAT operator to convert an object of the type Course to a collection of objects of the type OnsiteCourse.</span></span> <span data-ttu-id="87370-141">La query è basata sul [modello School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="87370-141">The query is based on the [School Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span></span>  
  
 <span data-ttu-id="87370-142">[! code-SQL [DP EntityServices Concepts # TREAT_ISOF] ~/samples/snippets/tsql/VS_Snippets_Data/dp EntityServices Concepts/TSQL/EntitySql. SQL # TREAT_ISOF)]</span><span class="sxs-lookup"><span data-stu-id="87370-142">[!code-sql[DP EntityServices Concepts#TREAT_ISOF]~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#treat_isof)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87370-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87370-143">See also</span></span>

- [<span data-ttu-id="87370-144">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="87370-144">Entity SQL Reference</span></span>](entity-sql-reference.md)
