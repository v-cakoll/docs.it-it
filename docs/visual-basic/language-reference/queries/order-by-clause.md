---
title: Clausola Order By
ms.date: 07/20/2015
f1_keywords:
- vb.QueryOrderBy
- vb.QueryAscending
- vb.QueryDescending
helpviewer_keywords:
- queries [Visual Basic], Order By
- Order By clause [Visual Basic]
- Order By statement [Visual Basic]
ms.assetid: fa911282-6b81-44c7-acfa-46b5bb93df75
ms.openlocfilehash: 63f454064e88bc18f252940f3abd8e59b8900e5b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359748"
---
# <a name="order-by-clause-visual-basic"></a><span data-ttu-id="2164c-102">Clausola Order By (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2164c-102">Order By Clause (Visual Basic)</span></span>
<span data-ttu-id="2164c-103">Specifica l'ordinamento per il risultato di una query.</span><span class="sxs-lookup"><span data-stu-id="2164c-103">Specifies the sort order for a query result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2164c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2164c-104">Syntax</span></span>  
  
```vb  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="2164c-105">Parti</span><span class="sxs-lookup"><span data-stu-id="2164c-105">Parts</span></span>  
 `orderExp1`  
 <span data-ttu-id="2164c-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="2164c-106">Required.</span></span> <span data-ttu-id="2164c-107">Uno o più campi dal risultato della query corrente che identificano la modalità di ordinamento dei valori restituiti.</span><span class="sxs-lookup"><span data-stu-id="2164c-107">One or more fields from the current query result that identify how to order the returned values.</span></span> <span data-ttu-id="2164c-108">I nomi dei campi devono essere separati da virgole (,).</span><span class="sxs-lookup"><span data-stu-id="2164c-108">The field names must be separated by commas (,).</span></span> <span data-ttu-id="2164c-109">È possibile identificare ogni campo come ordinato in ordine crescente o decrescente usando le `Ascending` `Descending` parole chiave o.</span><span class="sxs-lookup"><span data-stu-id="2164c-109">You can identify each field as sorted in ascending or descending order by using the `Ascending` or `Descending` keywords.</span></span> <span data-ttu-id="2164c-110">Se non `Ascending` `Descending` viene specificata alcuna parola chiave o, l'ordinamento predefinito è crescente.</span><span class="sxs-lookup"><span data-stu-id="2164c-110">If no `Ascending` or `Descending` keyword is specified, the default sort order is ascending.</span></span> <span data-ttu-id="2164c-111">Ai campi di ordinamento viene assegnata la precedenza da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="2164c-111">The sort order fields are given precedence from left to right.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2164c-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="2164c-112">Remarks</span></span>  
 <span data-ttu-id="2164c-113">È possibile utilizzare la `Order By` clausola per ordinare i risultati di una query.</span><span class="sxs-lookup"><span data-stu-id="2164c-113">You can use the `Order By` clause to sort the results of a query.</span></span> <span data-ttu-id="2164c-114">La `Order By` clausola può ordinare solo un risultato in base alla variabile di intervallo per l'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="2164c-114">The `Order By` clause can only sort a result based on the range variable for the current scope.</span></span> <span data-ttu-id="2164c-115">Ad esempio, la `Select` clausola introduce un nuovo ambito in un'espressione di query con nuove variabili di iterazione per tale ambito.</span><span class="sxs-lookup"><span data-stu-id="2164c-115">For example, the `Select` clause introduces a new scope in a query expression with new iteration variables for that scope.</span></span> <span data-ttu-id="2164c-116">Le variabili di intervallo definite prima `Select` di una clausola in una query non sono disponibili dopo la `Select` clausola.</span><span class="sxs-lookup"><span data-stu-id="2164c-116">Range variables defined before a `Select` clause in a query are not available after the `Select` clause.</span></span> <span data-ttu-id="2164c-117">Se pertanto si desidera ordinare i risultati in base a un campo non disponibile nella `Select` clausola, è necessario inserire la `Order By` clausola prima della `Select` clausola.</span><span class="sxs-lookup"><span data-stu-id="2164c-117">Therefore, if you want to order your results by a field that is not available in the `Select` clause, you must put the `Order By` clause before the `Select` clause.</span></span> <span data-ttu-id="2164c-118">Un esempio di quando è necessario eseguire questa operazione è quando si desidera ordinare la query in base a campi che non vengono restituiti come parte del risultato.</span><span class="sxs-lookup"><span data-stu-id="2164c-118">One example of when you would have to do this is when you want to sort your query by fields that are not returned as part of the result.</span></span>  
  
 <span data-ttu-id="2164c-119">L'ordine crescente e decrescente per un campo è determinato dall'implementazione dell' <xref:System.IComparable> interfaccia per il tipo di dati del campo.</span><span class="sxs-lookup"><span data-stu-id="2164c-119">Ascending and descending order for a field is determined by the implementation of the <xref:System.IComparable> interface for the data type of the field.</span></span> <span data-ttu-id="2164c-120">Se il tipo di dati non implementa l' <xref:System.IComparable> interfaccia, l'ordinamento viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="2164c-120">If the data type does not implement the <xref:System.IComparable> interface, the sort order is ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2164c-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="2164c-121">Example</span></span>  
 <span data-ttu-id="2164c-122">Nell'espressione di query seguente viene utilizzata una `From` clausola per dichiarare una variabile di intervallo `book` per la `books` raccolta.</span><span class="sxs-lookup"><span data-stu-id="2164c-122">The following query expression uses a `From` clause to declare a range variable `book` for the `books` collection.</span></span> <span data-ttu-id="2164c-123">La `Order By` clausola Ordina il risultato della query in base al prezzo in ordine crescente (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="2164c-123">The `Order By` clause sorts the query result by price in ascending order (the default).</span></span> <span data-ttu-id="2164c-124">I libri con lo stesso prezzo vengono ordinati in base al titolo in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="2164c-124">Books with the same price are sorted by title in ascending order.</span></span> <span data-ttu-id="2164c-125">La `Select` clausola seleziona le `Title` `Price` proprietà e come valori restituiti dalla query.</span><span class="sxs-lookup"><span data-stu-id="2164c-125">The `Select` clause selects the `Title` and `Price` properties as the values returned by the query.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#24)]  
  
## <a name="example"></a><span data-ttu-id="2164c-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="2164c-126">Example</span></span>  
 <span data-ttu-id="2164c-127">Nell'espressione di query seguente viene utilizzata la `Order By` clausola per ordinare il risultato della query in base al prezzo in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="2164c-127">The following query expression uses the `Order By` clause to sort the query result by price in descending order.</span></span> <span data-ttu-id="2164c-128">I libri con lo stesso prezzo vengono ordinati in base al titolo in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="2164c-128">Books with the same price are sorted by title in ascending order.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#25)]  
  
## <a name="example"></a><span data-ttu-id="2164c-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="2164c-129">Example</span></span>  
 <span data-ttu-id="2164c-130">Nell'espressione di query seguente viene utilizzata una `Select` clausola per selezionare titolo, prezzo, data di pubblicazione e autore.</span><span class="sxs-lookup"><span data-stu-id="2164c-130">The following query expression uses a `Select` clause to select the book title, price, publish date, and author.</span></span> <span data-ttu-id="2164c-131">Quindi compila i `Title` `Price` campi,, `PublishDate` e `Author` della variabile di intervallo per il nuovo ambito.</span><span class="sxs-lookup"><span data-stu-id="2164c-131">It then populates the `Title`, `Price`, `PublishDate`, and `Author` fields of the range variable for the new scope.</span></span> <span data-ttu-id="2164c-132">La `Order By` clausola Ordina la nuova variabile di intervallo in base al nome dell'autore, al titolo del libro e quindi al prezzo.</span><span class="sxs-lookup"><span data-stu-id="2164c-132">The `Order By` clause orders the new range variable by author name, book title, and then price.</span></span> <span data-ttu-id="2164c-133">Ogni colonna viene ordinata in base all'ordine predefinito (ascendente).</span><span class="sxs-lookup"><span data-stu-id="2164c-133">Each column is sorted in the default order (ascending).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="2164c-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2164c-134">See also</span></span>

- [<span data-ttu-id="2164c-135">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2164c-135">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="2164c-136">Query</span><span class="sxs-lookup"><span data-stu-id="2164c-136">Queries</span></span>](index.md)
- [<span data-ttu-id="2164c-137">Clausola SELECT</span><span class="sxs-lookup"><span data-stu-id="2164c-137">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="2164c-138">Clausola from</span><span class="sxs-lookup"><span data-stu-id="2164c-138">From Clause</span></span>](from-clause.md)
