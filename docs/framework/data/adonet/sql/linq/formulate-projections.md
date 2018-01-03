---
title: Formulare proiezioni
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: bb22ddd4882d9885c55301a6fdc6a0eb336b49af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="formulate-projections"></a><span data-ttu-id="54ed3-102">Formulare proiezioni</span><span class="sxs-lookup"><span data-stu-id="54ed3-102">Formulate Projections</span></span>
<span data-ttu-id="54ed3-103">Negli esempi seguenti viene illustrato come è possibile combinare l'istruzione `select` in C# e l'istruzione `Select` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] con altre funzionalità per formare proiezioni della query.</span><span class="sxs-lookup"><span data-stu-id="54ed3-103">The following examples show how the `select` statement in C# and `Select` statement in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] can be combined with other features to form query projections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54ed3-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="54ed3-104">Example</span></span>  
 <span data-ttu-id="54ed3-105">L'esempio seguente usa il `Select` clausola [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clausola in c#) per restituire una sequenza di nomi di contatti per `Customers`.</span><span class="sxs-lookup"><span data-stu-id="54ed3-105">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) to return a sequence of contact names for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a><span data-ttu-id="54ed3-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="54ed3-106">Example</span></span>  
 <span data-ttu-id="54ed3-107">L'esempio seguente usa il `Select` clausola [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clausola in c#) e *tipi anonimi* per restituire una sequenza di nomi di contatti e numeri di telefono per `Customers`.</span><span class="sxs-lookup"><span data-stu-id="54ed3-107">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and *anonymous types* to return a sequence of contact names and telephone numbers for `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a><span data-ttu-id="54ed3-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="54ed3-108">Example</span></span>  
 <span data-ttu-id="54ed3-109">L'esempio seguente usa il `Select` clausola [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clausola in c#) e *tipi anonimi* per restituire una sequenza di nomi e numeri di telefono per i dipendenti.</span><span class="sxs-lookup"><span data-stu-id="54ed3-109">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and *anonymous types* to return a sequence of names and telephone numbers for employees.</span></span> <span data-ttu-id="54ed3-110">Il `FirstName` e `LastName` campi vengono combinati in un singolo campo (`Name`) e `HomePhone` campo viene rinominato in `Phone` nella sequenza risultante.</span><span class="sxs-lookup"><span data-stu-id="54ed3-110">The `FirstName` and `LastName` fields are combined into a single field (`Name`), and the `HomePhone` field is renamed to `Phone` in the resulting sequence.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a><span data-ttu-id="54ed3-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="54ed3-111">Example</span></span>  
 <span data-ttu-id="54ed3-112">L'esempio seguente usa il `Select` clausola [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clausola in c#) e *tipi anonimi* per restituire una sequenza di tutti i `ProductID`s e un valore calcolato denominato `HalfPrice`.</span><span class="sxs-lookup"><span data-stu-id="54ed3-112">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and *anonymous types* to return a sequence of all `ProductID`s and a calculated value named `HalfPrice`.</span></span> <span data-ttu-id="54ed3-113">Questo valore viene impostato su `UnitPrice` e diviso per 2.</span><span class="sxs-lookup"><span data-stu-id="54ed3-113">This value is set to the `UnitPrice` divided by 2.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a><span data-ttu-id="54ed3-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="54ed3-114">Example</span></span>  
 <span data-ttu-id="54ed3-115">L'esempio seguente usa il `Select` clausola [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clausola in c#) e un *istruzione condizionale* per restituire una sequenza di disponibilità del prodotto e nome del prodotto.</span><span class="sxs-lookup"><span data-stu-id="54ed3-115">The following example uses the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and a *conditional statement* to return a sequence of product name and product availability.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a><span data-ttu-id="54ed3-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="54ed3-116">Example</span></span>  
 <span data-ttu-id="54ed3-117">Nell'esempio seguente viene utilizzato un [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] `Select` clausola (`select` clausola in c#) e un *tipo conosciuto* (Name) per restituire una sequenza di nomi dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="54ed3-117">The following example uses a [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] `Select` clause (`select` clause in C#) and a *known type* (Name) to return a sequence of the names of employees.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a><span data-ttu-id="54ed3-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="54ed3-118">Example</span></span>  
 <span data-ttu-id="54ed3-119">L'esempio seguente usa `Select` e `Where` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` e `where` in c#) per restituire un *sequenza filtrata* nomi di contatti per i clienti di Londra.</span><span class="sxs-lookup"><span data-stu-id="54ed3-119">The following example uses `Select` and `Where` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` and `where` in C#) to return a *filtered sequence* of contact names for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a><span data-ttu-id="54ed3-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="54ed3-120">Example</span></span>  
 <span data-ttu-id="54ed3-121">Nell'esempio seguente viene utilizzato un `Select` clausola [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clausola in c#) e *tipi anonimi* per restituire un *subset con shaping* dei dati sui clienti.</span><span class="sxs-lookup"><span data-stu-id="54ed3-121">The following example uses a `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) and *anonymous types* to return a *shaped subset* of the data about customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a><span data-ttu-id="54ed3-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="54ed3-122">Example</span></span>  
 <span data-ttu-id="54ed3-123">Nell'esempio seguente vengono usate query annidate per restituire i risultati riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="54ed3-123">The following example uses nested queries to return the following results:</span></span>  
  
-   <span data-ttu-id="54ed3-124">Una sequenza di tutti gli ordini e dei corrispondenti `OrderID`.</span><span class="sxs-lookup"><span data-stu-id="54ed3-124">A sequence of all orders and their corresponding `OrderID`s.</span></span>  
  
-   <span data-ttu-id="54ed3-125">Una sottosequenza degli elementi nell'ordine per cui è presente uno sconto.</span><span class="sxs-lookup"><span data-stu-id="54ed3-125">A subsequence of the items in the order for which there is a discount.</span></span>  
  
-   <span data-ttu-id="54ed3-126">L'importo risparmiato se il costo di spedizione non è incluso.</span><span class="sxs-lookup"><span data-stu-id="54ed3-126">The amount of money saved if the cost of shipping is not included.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a><span data-ttu-id="54ed3-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54ed3-127">See Also</span></span>  
 [<span data-ttu-id="54ed3-128">Esempi di query</span><span class="sxs-lookup"><span data-stu-id="54ed3-128">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
