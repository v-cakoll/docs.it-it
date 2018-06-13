---
title: Formulare proiezioni
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
ms.openlocfilehash: f554007bd8c9e69f6a8dc475c122d3fbdfc43a4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33364948"
---
# <a name="formulate-projections"></a><span data-ttu-id="e1a42-102">Formulare proiezioni</span><span class="sxs-lookup"><span data-stu-id="e1a42-102">Formulate Projections</span></span>
<span data-ttu-id="e1a42-103">Gli esempi seguenti illustrano il modo in cui `select` istruzione nel linguaggio c# e `Select` istruzione in Visual Basic può essere combinata con altre funzionalità per formare proiezioni della query.</span><span class="sxs-lookup"><span data-stu-id="e1a42-103">The following examples show how the `select` statement in C# and `Select` statement in Visual Basic can be combined with other features to form query projections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1a42-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="e1a42-104">Example</span></span>  
 <span data-ttu-id="e1a42-105">Nell'esempio seguente viene utilizzata la `Select` clausola in Visual Basic (`select` clausola in c#) per restituire una sequenza di nomi di contatti per `Customers`.</span><span class="sxs-lookup"><span data-stu-id="e1a42-105">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) to return a sequence of contact names for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a><span data-ttu-id="e1a42-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="e1a42-106">Example</span></span>  
 <span data-ttu-id="e1a42-107">Nell'esempio seguente viene utilizzata la `Select` clausola in Visual Basic (`select` clausola in c#) e *tipi anonimi* per restituire una sequenza di nomi di contatti e numeri di telefono per `Customers`.</span><span class="sxs-lookup"><span data-stu-id="e1a42-107">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of contact names and telephone numbers for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a><span data-ttu-id="e1a42-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="e1a42-108">Example</span></span>  
 <span data-ttu-id="e1a42-109">Nell'esempio seguente viene utilizzata la `Select` clausola in Visual Basic (`select` clausola in c#) e *tipi anonimi* per restituire una sequenza di nomi e i numeri di telefono per i dipendenti.</span><span class="sxs-lookup"><span data-stu-id="e1a42-109">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of names and telephone numbers for employees.</span></span> <span data-ttu-id="e1a42-110">Il `FirstName` e `LastName` campi vengono combinati in un singolo campo (`Name`) e `HomePhone` campo viene rinominato in `Phone` nella sequenza risultante.</span><span class="sxs-lookup"><span data-stu-id="e1a42-110">The `FirstName` and `LastName` fields are combined into a single field (`Name`), and the `HomePhone` field is renamed to `Phone` in the resulting sequence.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a><span data-ttu-id="e1a42-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="e1a42-111">Example</span></span>  
 <span data-ttu-id="e1a42-112">Nell'esempio seguente viene utilizzata la `Select` clausola in Visual Basic (`select` clausola in c#) e *tipi anonimi* per restituire una sequenza di tutti i `ProductID`s e un valore calcolato denominato `HalfPrice`.</span><span class="sxs-lookup"><span data-stu-id="e1a42-112">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a sequence of all `ProductID`s and a calculated value named `HalfPrice`.</span></span> <span data-ttu-id="e1a42-113">Questo valore viene impostato su `UnitPrice` e diviso per 2.</span><span class="sxs-lookup"><span data-stu-id="e1a42-113">This value is set to the `UnitPrice` divided by 2.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a><span data-ttu-id="e1a42-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="e1a42-114">Example</span></span>  
 <span data-ttu-id="e1a42-115">Nell'esempio seguente viene utilizzata la `Select` clausola in Visual Basic (`select` clausola in c#) e una *istruzione condizionale* per restituire una sequenza di disponibilità del prodotto e nome del prodotto.</span><span class="sxs-lookup"><span data-stu-id="e1a42-115">The following example uses the `Select` clause in Visual Basic (`select` clause in C#) and a *conditional statement* to return a sequence of product name and product availability.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a><span data-ttu-id="e1a42-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="e1a42-116">Example</span></span>  
 <span data-ttu-id="e1a42-117">Nell'esempio seguente viene utilizzato un Visual Basic `Select` clausola (`select` clausola in c#) e una *tipo conosciuto* (Name) per restituire una sequenza di nomi di dipendenti.</span><span class="sxs-lookup"><span data-stu-id="e1a42-117">The following example uses a Visual Basic `Select` clause (`select` clause in C#) and a *known type* (Name) to return a sequence of the names of employees.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a><span data-ttu-id="e1a42-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="e1a42-118">Example</span></span>  
 <span data-ttu-id="e1a42-119">Nell'esempio seguente viene utilizzata `Select` e `Where` in Visual Basic (`select` e `where` in c#) per restituire un *sequenza filtrata* di nomi di contatti per i clienti di Londra.</span><span class="sxs-lookup"><span data-stu-id="e1a42-119">The following example uses `Select` and `Where` in Visual Basic (`select` and `where` in C#) to return a *filtered sequence* of contact names for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a><span data-ttu-id="e1a42-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="e1a42-120">Example</span></span>  
 <span data-ttu-id="e1a42-121">L'esempio seguente usa un' `Select` clausola in Visual Basic (`select` clausola in c#) e *tipi anonimi* per restituire un *subset con shaping* dei dati sui clienti.</span><span class="sxs-lookup"><span data-stu-id="e1a42-121">The following example uses a `Select` clause in Visual Basic (`select` clause in C#) and *anonymous types* to return a *shaped subset* of the data about customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a><span data-ttu-id="e1a42-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="e1a42-122">Example</span></span>  
 <span data-ttu-id="e1a42-123">Nell'esempio seguente vengono usate query annidate per restituire i risultati riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="e1a42-123">The following example uses nested queries to return the following results:</span></span>  
  
-   <span data-ttu-id="e1a42-124">Una sequenza di tutti gli ordini e dei corrispondenti `OrderID`.</span><span class="sxs-lookup"><span data-stu-id="e1a42-124">A sequence of all orders and their corresponding `OrderID`s.</span></span>  
  
-   <span data-ttu-id="e1a42-125">Una sottosequenza degli elementi nell'ordine per cui è presente uno sconto.</span><span class="sxs-lookup"><span data-stu-id="e1a42-125">A subsequence of the items in the order for which there is a discount.</span></span>  
  
-   <span data-ttu-id="e1a42-126">L'importo risparmiato se il costo di spedizione non è incluso.</span><span class="sxs-lookup"><span data-stu-id="e1a42-126">The amount of money saved if the cost of shipping is not included.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a><span data-ttu-id="e1a42-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1a42-127">See Also</span></span>  
 [<span data-ttu-id="e1a42-128">Esempi di query</span><span class="sxs-lookup"><span data-stu-id="e1a42-128">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
