---
title: Clausola Distinct (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6ed92d5d601c1ec329728346ac881c4fa2bad8aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="distinct-clause-visual-basic"></a><span data-ttu-id="68845-102">Clausola Distinct (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68845-102">Distinct Clause (Visual Basic)</span></span>
<span data-ttu-id="68845-103">Limita i valori della variabile di intervallo corrente per eliminare i valori duplicati nelle clausole di query successive.</span><span class="sxs-lookup"><span data-stu-id="68845-103">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68845-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="68845-104">Syntax</span></span>  
  
```  
Distinct  
```  
  
## <a name="remarks"></a><span data-ttu-id="68845-105">Note</span><span class="sxs-lookup"><span data-stu-id="68845-105">Remarks</span></span>  
 <span data-ttu-id="68845-106">È possibile utilizzare il `Distinct` clausola per restituire un elenco di elementi univoci.</span><span class="sxs-lookup"><span data-stu-id="68845-106">You can use the `Distinct` clause to return a list of unique items.</span></span> <span data-ttu-id="68845-107">Il `Distinct` clausola, la query di ignorare i risultati di query duplicata.</span><span class="sxs-lookup"><span data-stu-id="68845-107">The `Distinct` clause causes the query to ignore duplicate query results.</span></span> <span data-ttu-id="68845-108">Il `Distinct` clausola viene applicata ai valori duplicati per tutti i campi specificati dalla restituiti il `Select` clausola.</span><span class="sxs-lookup"><span data-stu-id="68845-108">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span></span> <span data-ttu-id="68845-109">Se non `Select` clausola viene specificata, il `Distinct` clausola viene applicata alla variabile di intervallo per la query identificata nella `From` clausola.</span><span class="sxs-lookup"><span data-stu-id="68845-109">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span></span> <span data-ttu-id="68845-110">Se la variabile di intervallo non è un tipo immutabile, la query ignorerà un risultato della query solo se tutti i membri del tipo corrispondano a un risultato della query esistente.</span><span class="sxs-lookup"><span data-stu-id="68845-110">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68845-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="68845-111">Example</span></span>  
 <span data-ttu-id="68845-112">L'espressione di query seguente unisce in join un elenco di clienti e un elenco di ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="68845-112">The following query expression joins a list of customers and a list of customer orders.</span></span> <span data-ttu-id="68845-113">Il `Distinct` clausola viene inclusa per restituire un elenco di nomi di clienti univoci e Data ordine.</span><span class="sxs-lookup"><span data-stu-id="68845-113">The `Distinct` clause is included to return a list of unique customer names and order dates.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#20](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/distinct-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="68845-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68845-114">See Also</span></span>  
 [<span data-ttu-id="68845-115">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="68845-115">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="68845-116">Query</span><span class="sxs-lookup"><span data-stu-id="68845-116">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="68845-117">Clausola From</span><span class="sxs-lookup"><span data-stu-id="68845-117">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="68845-118">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="68845-118">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="68845-119">Clausola Where</span><span class="sxs-lookup"><span data-stu-id="68845-119">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
