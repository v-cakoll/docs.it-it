---
title: Introduzione
description: Con questo esempio di codice, iniziare a utilizzare LINQ to SQL per utilizzare la tecnologia LINQ per accedere ai database SQL Analogamente all'accesso a una raccolta in memoria.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
ms.openlocfilehash: a46c42e917bdab0d32ee594bbcd604ee9e3d26bc
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286417"
---
# <a name="getting-started"></a><span data-ttu-id="a7818-103">Introduzione</span><span class="sxs-lookup"><span data-stu-id="a7818-103">Getting Started</span></span>
<span data-ttu-id="a7818-104">Utilizzando [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , è possibile utilizzare la tecnologia LINQ per accedere ai database SQL Analogamente all'accesso a una raccolta in memoria.</span><span class="sxs-lookup"><span data-stu-id="a7818-104">By using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you can use the LINQ technology to access SQL databases just as you would access an in-memory collection.</span></span>  
  
 <span data-ttu-id="a7818-105">Ad esempio, l'oggetto `nw` nel codice seguente viene creato per rappresentare il database `Northwind`, viene usata `Customers` come tabella di destinazione, le righe vengono filtrate in base a `Customers` residenti a `London` e viene selezionata una stringa da recuperare relativa a `CompanyName`.</span><span class="sxs-lookup"><span data-stu-id="a7818-105">For example, the `nw` object in the following code is created to represent the `Northwind` database, the `Customers` table is targeted, the rows are filtered for `Customers` from `London`, and a string for `CompanyName` is selected for retrieval.</span></span>  
  
 <span data-ttu-id="a7818-106">Quando viene eseguito il ciclo, viene recuperata la raccolta di valori `CompanyName`.</span><span class="sxs-lookup"><span data-stu-id="a7818-106">When the loop is executed, the collection of `CompanyName` values is retrieved.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a><span data-ttu-id="a7818-107">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="a7818-107">Next Steps</span></span>  
 <span data-ttu-id="a7818-108">Per alcuni esempi aggiuntivi, tra cui l'inserimento e l'aggiornamento, vedere [le operazioni che è possibile eseguire con LINQ to SQL](what-you-can-do-with-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a7818-108">For some additional examples, including inserting and updating, see [What You Can Do With LINQ to SQL](what-you-can-do-with-linq-to-sql.md).</span></span>  
  
 <span data-ttu-id="a7818-109">Provare quindi a eseguire alcune procedure dettagliate ed esercitazioni per acquisire un'esperienza pratica relativa all'utilizzo di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7818-109">Next, try some walkthroughs and tutorials to have a hands-on experience of using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="a7818-110">Vedere [learning by Walkthroughs](learning-by-walkthroughs.md).</span><span class="sxs-lookup"><span data-stu-id="a7818-110">See [Learning by Walkthroughs](learning-by-walkthroughs.md).</span></span>  
  
 <span data-ttu-id="a7818-111">Infine, informazioni su come iniziare a usare il proprio [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] progetto leggendo i [passaggi tipici per l'uso di LINQ to SQL](typical-steps-for-using-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a7818-111">Finally, learn how to get started on your own [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project by reading [Typical Steps for Using LINQ to SQL](typical-steps-for-using-linq-to-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7818-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7818-112">See also</span></span>

- [<span data-ttu-id="a7818-113">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="a7818-113">LINQ to SQL</span></span>](index.md)
- [<span data-ttu-id="a7818-114">Introduzione a LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="a7818-114">Introduction to LINQ (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="a7818-115">Introduzione a LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7818-115">Introduction to LINQ (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)
- [<span data-ttu-id="a7818-116">Il modello a oggetti di LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="a7818-116">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
