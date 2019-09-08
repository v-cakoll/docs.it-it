---
title: Introduzione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
ms.openlocfilehash: bd82b7e83149aaa53cf1b240cb79f8747bccba47
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793908"
---
# <a name="getting-started"></a><span data-ttu-id="5a912-102">Introduzione</span><span class="sxs-lookup"><span data-stu-id="5a912-102">Getting Started</span></span>
<span data-ttu-id="5a912-103">Utilizzando [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], è possibile utilizzare la [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] tecnologia per accedere ai database SQL Analogamente all'accesso a una raccolta in memoria.</span><span class="sxs-lookup"><span data-stu-id="5a912-103">By using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you can use the [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] technology to access SQL databases just as you would access an in-memory collection.</span></span>  
  
 <span data-ttu-id="5a912-104">Ad esempio, l'oggetto `nw` nel codice seguente viene creato per rappresentare il database `Northwind`, viene usata `Customers` come tabella di destinazione, le righe vengono filtrate in base a `Customers` residenti a `London` e viene selezionata una stringa da recuperare relativa a `CompanyName`.</span><span class="sxs-lookup"><span data-stu-id="5a912-104">For example, the `nw` object in the following code is created to represent the `Northwind` database, the `Customers` table is targeted, the rows are filtered for `Customers` from `London`, and a string for `CompanyName` is selected for retrieval.</span></span>  
  
 <span data-ttu-id="5a912-105">Quando viene eseguito il ciclo, viene recuperata la raccolta di valori `CompanyName`.</span><span class="sxs-lookup"><span data-stu-id="5a912-105">When the loop is executed, the collection of `CompanyName` values is retrieved.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a><span data-ttu-id="5a912-106">Fasi successive</span><span class="sxs-lookup"><span data-stu-id="5a912-106">Next Steps</span></span>  
 <span data-ttu-id="5a912-107">Per alcuni esempi aggiuntivi, tra cui l'inserimento e l'aggiornamento, vedere [le operazioni che è possibile eseguire con LINQ to SQL](what-you-can-do-with-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="5a912-107">For some additional examples, including inserting and updating, see [What You Can Do With LINQ to SQL](what-you-can-do-with-linq-to-sql.md).</span></span>  
  
 <span data-ttu-id="5a912-108">Provare quindi a eseguire alcune procedure dettagliate ed esercitazioni per acquisire un'esperienza pratica relativa all'utilizzo di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a912-108">Next, try some walkthroughs and tutorials to have a hands-on experience of using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="5a912-109">Vedere [learning by Walkthroughs](learning-by-walkthroughs.md).</span><span class="sxs-lookup"><span data-stu-id="5a912-109">See [Learning by Walkthroughs](learning-by-walkthroughs.md).</span></span>  
  
 <span data-ttu-id="5a912-110">Infine, informazioni su come iniziare a usare il proprio [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] progetto leggendo i [passaggi tipici per l'uso di LINQ to SQL](typical-steps-for-using-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="5a912-110">Finally, learn how to get started on your own [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project by reading [Typical Steps for Using LINQ to SQL](typical-steps-for-using-linq-to-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a912-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a912-111">See also</span></span>

- [<span data-ttu-id="5a912-112">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="5a912-112">LINQ to SQL</span></span>](index.md)
- [<span data-ttu-id="5a912-113">Introduzione a LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="5a912-113">Introduction to LINQ (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="5a912-114">Introduzione a LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a912-114">Introduction to LINQ (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)
- [<span data-ttu-id="5a912-115">Modello a oggetti LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="5a912-115">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
