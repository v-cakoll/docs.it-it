---
title: Clausola Order By (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QueryOrderBy
- vb.QueryAscending
- vb.QueryDescending
helpviewer_keywords:
- queries [Visual Basic], Order By
- Order By clause [Visual Basic]
- Order By statement [Visual Basic]
ms.assetid: fa911282-6b81-44c7-acfa-46b5bb93df75
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 21ee21942b966668a67b14aba72b8f9fc5ee903c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="order-by-clause-visual-basic"></a><span data-ttu-id="223f9-102">Clausola Order By (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="223f9-102">Order By Clause (Visual Basic)</span></span>
<span data-ttu-id="223f9-103">Specifica l'ordinamento dei risultati di una query.</span><span class="sxs-lookup"><span data-stu-id="223f9-103">Specifies the sort order for a query result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="223f9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="223f9-104">Syntax</span></span>  
  
```  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="223f9-105">Parti</span><span class="sxs-lookup"><span data-stu-id="223f9-105">Parts</span></span>  
 `orderExp1`  
 <span data-ttu-id="223f9-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="223f9-106">Required.</span></span> <span data-ttu-id="223f9-107">Uno o più campi dai risultati della query corrente che specificano come ordinare i valori restituiti.</span><span class="sxs-lookup"><span data-stu-id="223f9-107">One or more fields from the current query result that identify how to order the returned values.</span></span> <span data-ttu-id="223f9-108">I nomi dei campi devono essere separati da virgole (,).</span><span class="sxs-lookup"><span data-stu-id="223f9-108">The field names must be separated by commas (,).</span></span> <span data-ttu-id="223f9-109">È possibile identificare ogni campo, come ordinato in ordine crescente o decrescente utilizzando il `Ascending` o `Descending` parole chiave.</span><span class="sxs-lookup"><span data-stu-id="223f9-109">You can identify each field as sorted in ascending or descending order by using the `Ascending` or `Descending` keywords.</span></span> <span data-ttu-id="223f9-110">Se non `Ascending` o `Descending` (parola chiave) è specificato, l'ordinamento predefinito è crescente.</span><span class="sxs-lookup"><span data-stu-id="223f9-110">If no `Ascending` or `Descending` keyword is specified, the default sort order is ascending.</span></span> <span data-ttu-id="223f9-111">I campi di ordinamento ha la precedenza da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="223f9-111">The sort order fields are given precedence from left to right.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="223f9-112">Note</span><span class="sxs-lookup"><span data-stu-id="223f9-112">Remarks</span></span>  
 <span data-ttu-id="223f9-113">È possibile utilizzare il `Order By` clausola per ordinare i risultati di una query.</span><span class="sxs-lookup"><span data-stu-id="223f9-113">You can use the `Order By` clause to sort the results of a query.</span></span> <span data-ttu-id="223f9-114">Il `Order By` clausola può ordinare solo un risultato in base alla variabile di intervallo per l'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="223f9-114">The `Order By` clause can only sort a result based on the range variable for the current scope.</span></span> <span data-ttu-id="223f9-115">Ad esempio, il `Select` clausola introduce un nuovo ambito in un'espressione di query con nuove variabili di iterazione per tale ambito.</span><span class="sxs-lookup"><span data-stu-id="223f9-115">For example, the `Select` clause introduces a new scope in a query expression with new iteration variables for that scope.</span></span> <span data-ttu-id="223f9-116">Le variabili definite prima di intervallo un `Select` in una query non sono disponibili dopo il `Select` clausola.</span><span class="sxs-lookup"><span data-stu-id="223f9-116">Range variables defined before a `Select` clause in a query are not available after the `Select` clause.</span></span> <span data-ttu-id="223f9-117">Pertanto, se si desidera ordinare i risultati in base a un campo che non è disponibile nel `Select` clausola, è necessario inserire il `Order By` clausola prima il `Select` clausola.</span><span class="sxs-lookup"><span data-stu-id="223f9-117">Therefore, if you want to order your results by a field that is not available in the `Select` clause, you must put the `Order By` clause before the `Select` clause.</span></span> <span data-ttu-id="223f9-118">Un esempio di quando è necessario eseguire questa operazione è quando si desidera ordinare la query per i campi che non vengono restituiti come parte del risultato.</span><span class="sxs-lookup"><span data-stu-id="223f9-118">One example of when you would have to do this is when you want to sort your query by fields that are not returned as part of the result.</span></span>  
  
 <span data-ttu-id="223f9-119">Ordinamento crescente e decrescente per un campo è determinato dall'implementazione del <xref:System.IComparable> interfaccia per il tipo di dati del campo.</span><span class="sxs-lookup"><span data-stu-id="223f9-119">Ascending and descending order for a field is determined by the implementation of the <xref:System.IComparable> interface for the data type of the field.</span></span> <span data-ttu-id="223f9-120">Se il tipo di dati non implementa il <xref:System.IComparable> interfaccia, l'ordinamento viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="223f9-120">If the data type does not implement the <xref:System.IComparable> interface, the sort order is ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="223f9-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="223f9-121">Example</span></span>  
 <span data-ttu-id="223f9-122">La query seguente espressione utilizza un `From` clausola per dichiarare una variabile di intervallo `book` per il `books` insieme.</span><span class="sxs-lookup"><span data-stu-id="223f9-122">The following query expression uses a `From` clause to declare a range variable `book` for the `books` collection.</span></span> <span data-ttu-id="223f9-123">Il `Order By` clausola ordina i risultati della query in base al prezzo in senso crescente (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="223f9-123">The `Order By` clause sorts the query result by price in ascending order (the default).</span></span> <span data-ttu-id="223f9-124">Documentazione con lo stesso prezzo vengono ordinati in base a titolo in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="223f9-124">Books with the same price are sorted by title in ascending order.</span></span> <span data-ttu-id="223f9-125">Il `Select` clausola seleziona il `Title` e `Price` proprietà come valori restituiti dalla query.</span><span class="sxs-lookup"><span data-stu-id="223f9-125">The `Select` clause selects the `Title` and `Price` properties as the values returned by the query.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#24](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="223f9-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="223f9-126">Example</span></span>  
 <span data-ttu-id="223f9-127">La query seguente espressione utilizza la `Order By` clausola per ordinare il risultato della query in base al prezzo in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="223f9-127">The following query expression uses the `Order By` clause to sort the query result by price in descending order.</span></span> <span data-ttu-id="223f9-128">Documentazione con lo stesso prezzo vengono ordinati in base a titolo in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="223f9-128">Books with the same price are sorted by title in ascending order.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#25](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="223f9-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="223f9-129">Example</span></span>  
 <span data-ttu-id="223f9-130">La query seguente espressione utilizza un `Select` clausola per selezionare il titolo del libro, prezzo, data di pubblicazione e la creazione.</span><span class="sxs-lookup"><span data-stu-id="223f9-130">The following query expression uses a `Select` clause to select the book title, price, publish date, and author.</span></span> <span data-ttu-id="223f9-131">Viene quindi popolato il `Title`, `Price`, `PublishDate`, e `Author` campi della variabile di intervallo per il nuovo ambito.</span><span class="sxs-lookup"><span data-stu-id="223f9-131">It then populates the `Title`, `Price`, `PublishDate`, and `Author` fields of the range variable for the new scope.</span></span> <span data-ttu-id="223f9-132">Il `Order By` clausola ordina la nuova variabile di intervallo per il nome dell'autore, titolo del libro e prezzo.</span><span class="sxs-lookup"><span data-stu-id="223f9-132">The `Order By` clause orders the new range variable by author name, book title, and then price.</span></span> <span data-ttu-id="223f9-133">Ogni colonna viene ordinata in ordine predefinito (crescente).</span><span class="sxs-lookup"><span data-stu-id="223f9-133">Each column is sorted in the default order (ascending).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#26](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="223f9-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="223f9-134">See Also</span></span>  
 [<span data-ttu-id="223f9-135">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="223f9-135">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="223f9-136">Query</span><span class="sxs-lookup"><span data-stu-id="223f9-136">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="223f9-137">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="223f9-137">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="223f9-138">Clausola From</span><span class="sxs-lookup"><span data-stu-id="223f9-138">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
