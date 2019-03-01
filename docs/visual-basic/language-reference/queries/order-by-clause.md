---
title: Clausola Order By (Visual Basic)
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
ms.openlocfilehash: 1d9055796687f828cc173a78feb9918cbf70bbd8
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56976369"
---
# <a name="order-by-clause-visual-basic"></a><span data-ttu-id="ec471-102">Clausola Order By (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec471-102">Order By Clause (Visual Basic)</span></span>
<span data-ttu-id="ec471-103">Specifica l'ordinamento dei risultati della query.</span><span class="sxs-lookup"><span data-stu-id="ec471-103">Specifies the sort order for a query result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec471-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ec471-104">Syntax</span></span>  
  
```  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="ec471-105">Parti</span><span class="sxs-lookup"><span data-stu-id="ec471-105">Parts</span></span>  
 `orderExp1`  
 <span data-ttu-id="ec471-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ec471-106">Required.</span></span> <span data-ttu-id="ec471-107">Uno o più campi dai risultati della query corrente che identificano come ordinare i valori restituiti.</span><span class="sxs-lookup"><span data-stu-id="ec471-107">One or more fields from the current query result that identify how to order the returned values.</span></span> <span data-ttu-id="ec471-108">I nomi dei campi devono essere separati da virgole (,).</span><span class="sxs-lookup"><span data-stu-id="ec471-108">The field names must be separated by commas (,).</span></span> <span data-ttu-id="ec471-109">È possibile identificare ogni campo, come ordinato in ordine crescente o decrescente usando la `Ascending` o `Descending` parole chiave.</span><span class="sxs-lookup"><span data-stu-id="ec471-109">You can identify each field as sorted in ascending or descending order by using the `Ascending` or `Descending` keywords.</span></span> <span data-ttu-id="ec471-110">Se nessun `Ascending` o `Descending` (parola chiave) viene specificato, l'ordinamento predefinito è crescente.</span><span class="sxs-lookup"><span data-stu-id="ec471-110">If no `Ascending` or `Descending` keyword is specified, the default sort order is ascending.</span></span> <span data-ttu-id="ec471-111">I campi di ordinamento ha la precedenza da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="ec471-111">The sort order fields are given precedence from left to right.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec471-112">Note</span><span class="sxs-lookup"><span data-stu-id="ec471-112">Remarks</span></span>  
 <span data-ttu-id="ec471-113">È possibile usare il `Order By` clausola per ordinare i risultati di una query.</span><span class="sxs-lookup"><span data-stu-id="ec471-113">You can use the `Order By` clause to sort the results of a query.</span></span> <span data-ttu-id="ec471-114">Il `Order By` clausola solo possibile ordinare un risultato basato sulla variabile di intervallo per l'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="ec471-114">The `Order By` clause can only sort a result based on the range variable for the current scope.</span></span> <span data-ttu-id="ec471-115">Ad esempio, il `Select` clausola introduce un nuovo ambito in un'espressione di query con nuove variabili di iterazione per tale ambito.</span><span class="sxs-lookup"><span data-stu-id="ec471-115">For example, the `Select` clause introduces a new scope in a query expression with new iteration variables for that scope.</span></span> <span data-ttu-id="ec471-116">Le variabili definite prima di intervallo un `Select` clausola in una query non sono disponibili dopo il `Select` clausola.</span><span class="sxs-lookup"><span data-stu-id="ec471-116">Range variables defined before a `Select` clause in a query are not available after the `Select` clause.</span></span> <span data-ttu-id="ec471-117">Pertanto, se si desidera ordinare i risultati tramite un campo che non è disponibile nel `Select` clausola, è necessario inserire il `Order By` clausola prima il `Select` clausola.</span><span class="sxs-lookup"><span data-stu-id="ec471-117">Therefore, if you want to order your results by a field that is not available in the `Select` clause, you must put the `Order By` clause before the `Select` clause.</span></span> <span data-ttu-id="ec471-118">Un esempio di quando è necessario eseguire questa operazione è quando si desidera ordinare query in base a campi che non vengono restituiti come parte del risultato.</span><span class="sxs-lookup"><span data-stu-id="ec471-118">One example of when you would have to do this is when you want to sort your query by fields that are not returned as part of the result.</span></span>  
  
 <span data-ttu-id="ec471-119">Ordine crescente o decrescente per un campo è determinato dall'implementazione del <xref:System.IComparable> interfaccia per il tipo di dati del campo.</span><span class="sxs-lookup"><span data-stu-id="ec471-119">Ascending and descending order for a field is determined by the implementation of the <xref:System.IComparable> interface for the data type of the field.</span></span> <span data-ttu-id="ec471-120">Se il tipo di dati non implementa il <xref:System.IComparable> interfaccia, l'ordinamento viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="ec471-120">If the data type does not implement the <xref:System.IComparable> interface, the sort order is ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec471-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="ec471-121">Example</span></span>  
 <span data-ttu-id="ec471-122">La query seguente espressione Usa un `From` clausola per dichiarare una variabile di intervallo `book` per il `books` raccolta.</span><span class="sxs-lookup"><span data-stu-id="ec471-122">The following query expression uses a `From` clause to declare a range variable `book` for the `books` collection.</span></span> <span data-ttu-id="ec471-123">Il `Order By` clausola consente di ordinare i risultati della query in base al prezzo in modo crescente (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="ec471-123">The `Order By` clause sorts the query result by price in ascending order (the default).</span></span> <span data-ttu-id="ec471-124">Documentazione con lo stesso prezzo sono ordinati per titolo in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="ec471-124">Books with the same price are sorted by title in ascending order.</span></span> <span data-ttu-id="ec471-125">Il `Select` clausola consente di selezionare il `Title` e `Price` proprietà come valori restituiti dalla query.</span><span class="sxs-lookup"><span data-stu-id="ec471-125">The `Select` clause selects the `Title` and `Price` properties as the values returned by the query.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#24)]  
  
## <a name="example"></a><span data-ttu-id="ec471-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="ec471-126">Example</span></span>  
 <span data-ttu-id="ec471-127">La query seguente Usa espressione di `Order By` clausola per ordinare i risultati della query in base al prezzo in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="ec471-127">The following query expression uses the `Order By` clause to sort the query result by price in descending order.</span></span> <span data-ttu-id="ec471-128">Documentazione con lo stesso prezzo sono ordinati per titolo in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="ec471-128">Books with the same price are sorted by title in ascending order.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#25)]  
  
## <a name="example"></a><span data-ttu-id="ec471-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="ec471-129">Example</span></span>  
 <span data-ttu-id="ec471-130">La query seguente espressione utilizza un `Select` clausola per selezionare il titolo del libro, prezzo, data di pubblicazione e la creazione.</span><span class="sxs-lookup"><span data-stu-id="ec471-130">The following query expression uses a `Select` clause to select the book title, price, publish date, and author.</span></span> <span data-ttu-id="ec471-131">Viene quindi popolato il `Title`, `Price`, `PublishDate`, e `Author` campi della variabile di intervallo per il nuovo ambito.</span><span class="sxs-lookup"><span data-stu-id="ec471-131">It then populates the `Title`, `Price`, `PublishDate`, and `Author` fields of the range variable for the new scope.</span></span> <span data-ttu-id="ec471-132">Il `Order By` clausola ordina la nuova variabile di intervallo per il nome dell'autore, titolo del libro e prezzo.</span><span class="sxs-lookup"><span data-stu-id="ec471-132">The `Order By` clause orders the new range variable by author name, book title, and then price.</span></span> <span data-ttu-id="ec471-133">Ogni colonna è ordinata l'ordine predefinito (crescente).</span><span class="sxs-lookup"><span data-stu-id="ec471-133">Each column is sorted in the default order (ascending).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="ec471-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec471-134">See also</span></span>
- [<span data-ttu-id="ec471-135">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ec471-135">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="ec471-136">Query</span><span class="sxs-lookup"><span data-stu-id="ec471-136">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="ec471-137">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="ec471-137">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="ec471-138">Clausola From</span><span class="sxs-lookup"><span data-stu-id="ec471-138">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
