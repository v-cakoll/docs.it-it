---
title: Clausola Group By (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryGroupByInto
- vb.QueryGroupBy
- vb.QueryGroupRef
- vb.QueryGroupInto
- vb.QueryGroup
helpviewer_keywords:
- queries [Visual Basic], Group By
- Group By statement [Visual Basic]
- Group By clause [Visual Basic]
ms.assetid: b1b5dcea-6654-473b-a2db-01f7e4c265d7
ms.openlocfilehash: 47db8c9dc0562f8eb527eda65bb56404dc1ea8c8
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56971325"
---
# <a name="group-by-clause-visual-basic"></a><span data-ttu-id="5a82f-102">Clausola Group By (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a82f-102">Group By Clause (Visual Basic)</span></span>
<span data-ttu-id="5a82f-103">Raggruppa gli elementi di un risultato della query.</span><span class="sxs-lookup"><span data-stu-id="5a82f-103">Groups the elements of a query result.</span></span> <span data-ttu-id="5a82f-104">Può essere usata anche per applicare funzioni di aggregazione a ogni gruppo.</span><span class="sxs-lookup"><span data-stu-id="5a82f-104">Can also be used to apply aggregate functions to each group.</span></span> <span data-ttu-id="5a82f-105">L'operazione di raggruppamento è basata su una o più chiavi.</span><span class="sxs-lookup"><span data-stu-id="5a82f-105">The grouping operation is based on one or more keys.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a82f-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5a82f-106">Syntax</span></span>  
  
```  
Group [ listField1 [, listField2 [...] ] By keyExp1 [, keyExp2 [...] ]  
  Into aggregateList  
```  
  
## <a name="parts"></a><span data-ttu-id="5a82f-107">Parti</span><span class="sxs-lookup"><span data-stu-id="5a82f-107">Parts</span></span>  
  
-   <span data-ttu-id="5a82f-108">`listField1`, `listField2`</span><span class="sxs-lookup"><span data-stu-id="5a82f-108">`listField1`, `listField2`</span></span>  
  
     <span data-ttu-id="5a82f-109">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5a82f-109">Optional.</span></span> <span data-ttu-id="5a82f-110">Uno o più campi della variabile o delle variabili di query che identificano in modo esplicito i campi da includere nel risultato raggruppato.</span><span class="sxs-lookup"><span data-stu-id="5a82f-110">One or more fields of the query variable or variables that explicitly identify the fields to be included in the grouped result.</span></span> <span data-ttu-id="5a82f-111">Se non sono specificati campi, tutti i campi della variabile o delle variabili di query vengono inclusi nel risultato raggruppato.</span><span class="sxs-lookup"><span data-stu-id="5a82f-111">If no fields are specified, all fields of the query variable or variables are included in the grouped result.</span></span>  
  
-   `keyExp1`  
  
     <span data-ttu-id="5a82f-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5a82f-112">Required.</span></span> <span data-ttu-id="5a82f-113">Espressione che identifica la chiave da usare per determinare i gruppi di elementi.</span><span class="sxs-lookup"><span data-stu-id="5a82f-113">An expression that identifies the key to use to determine the groups of elements.</span></span> <span data-ttu-id="5a82f-114">È possibile specificare più di una chiave per specificare una chiave composta.</span><span class="sxs-lookup"><span data-stu-id="5a82f-114">You can specify more than one key to specify a composite key.</span></span>  
  
-   `keyExp2`  
  
     <span data-ttu-id="5a82f-115">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5a82f-115">Optional.</span></span> <span data-ttu-id="5a82f-116">Uno o più tasti aggiuntivi che vengono combinati con `keyExp1` per creare una chiave composta.</span><span class="sxs-lookup"><span data-stu-id="5a82f-116">One or more additional keys that are combined with `keyExp1` to create a composite key.</span></span>  
  
-   `aggregateList`  
  
     <span data-ttu-id="5a82f-117">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5a82f-117">Required.</span></span> <span data-ttu-id="5a82f-118">Una o più espressioni che identificano come vengono aggregati i gruppi.</span><span class="sxs-lookup"><span data-stu-id="5a82f-118">One or more expressions that identify how the groups are aggregated.</span></span> <span data-ttu-id="5a82f-119">Per identificare un nome di membro per i risultati raggruppati, usare la parola chiave `Group` , che può essere in uno dei seguenti formati:</span><span class="sxs-lookup"><span data-stu-id="5a82f-119">To identify a member name for the grouped results, use the `Group` keyword, which can be in either of the following forms:</span></span>  
  
    ```  
    Into Group  
    ```  
  
     <span data-ttu-id="5a82f-120">-oppure-</span><span class="sxs-lookup"><span data-stu-id="5a82f-120">-or-</span></span>  
  
    ```  
    Into <alias> = Group  
    ```  
  
     <span data-ttu-id="5a82f-121">È anche possibile includere funzioni di aggregazione da applicare al gruppo.</span><span class="sxs-lookup"><span data-stu-id="5a82f-121">You can also include aggregate functions to apply to the group.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a82f-122">Note</span><span class="sxs-lookup"><span data-stu-id="5a82f-122">Remarks</span></span>  
 <span data-ttu-id="5a82f-123">È possibile usare la clausola `Group By` per suddividere i risultati di una query in gruppi.</span><span class="sxs-lookup"><span data-stu-id="5a82f-123">You can use the `Group By` clause to break the results of a query into groups.</span></span> <span data-ttu-id="5a82f-124">Il raggruppamento è basato su una chiave o una chiave composta costituita da più chiavi.</span><span class="sxs-lookup"><span data-stu-id="5a82f-124">The grouping is based on a key or a composite key consisting of multiple keys.</span></span> <span data-ttu-id="5a82f-125">Gli elementi associati ai valori della chiave corrispondenti vengono inclusi nello stesso gruppo.</span><span class="sxs-lookup"><span data-stu-id="5a82f-125">Elements that are associated with matching key values are included in the same group.</span></span>  
  
 <span data-ttu-id="5a82f-126">Per identificare il nome del membro che viene usato per fare riferimento al gruppo, usare il parametro `aggregateList` della clausola `Into` e la parola chiave `Group` .</span><span class="sxs-lookup"><span data-stu-id="5a82f-126">You use the `aggregateList` parameter of the `Into` clause and the `Group` keyword to identify the member name that is used to reference the group.</span></span> <span data-ttu-id="5a82f-127">È anche possibile includere funzioni di aggregazione nella clausola `Into` per calcolare i valori per gli elementi raggruppati.</span><span class="sxs-lookup"><span data-stu-id="5a82f-127">You can also include aggregate functions in the `Into` clause to compute values for the grouped elements.</span></span> <span data-ttu-id="5a82f-128">Per un elenco di funzioni di aggregazione standard, vedere [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span><span class="sxs-lookup"><span data-stu-id="5a82f-128">For a list of standard aggregate functions, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a82f-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="5a82f-129">Example</span></span>  
 <span data-ttu-id="5a82f-130">L'esempio di codice seguente raggruppa un elenco di clienti in base alla località (paese) e fornisce un conteggio dei clienti in ogni gruppo.</span><span class="sxs-lookup"><span data-stu-id="5a82f-130">The following code example groups a list of customers based on their location (country) and provides a count of the customers in each group.</span></span> <span data-ttu-id="5a82f-131">I risultati vengono ordinati in base al nome del paese.</span><span class="sxs-lookup"><span data-stu-id="5a82f-131">The results are ordered by country name.</span></span> <span data-ttu-id="5a82f-132">I risultati raggruppati vengono ordinati in base al nome della città.</span><span class="sxs-lookup"><span data-stu-id="5a82f-132">The grouped results are ordered by city name.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="5a82f-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a82f-133">See also</span></span>
- [<span data-ttu-id="5a82f-134">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5a82f-134">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="5a82f-135">Query</span><span class="sxs-lookup"><span data-stu-id="5a82f-135">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="5a82f-136">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="5a82f-136">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="5a82f-137">Clausola From</span><span class="sxs-lookup"><span data-stu-id="5a82f-137">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="5a82f-138">Clausola Order By</span><span class="sxs-lookup"><span data-stu-id="5a82f-138">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="5a82f-139">Clausola Aggregate</span><span class="sxs-lookup"><span data-stu-id="5a82f-139">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="5a82f-140">Clausola Group Join</span><span class="sxs-lookup"><span data-stu-id="5a82f-140">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)
