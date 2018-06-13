---
title: Introduzione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
ms.openlocfilehash: 2358869d90baa82d4d51206b4ec1915a60b9a0f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33360031"
---
# <a name="getting-started"></a><span data-ttu-id="3fab1-102">Introduzione</span><span class="sxs-lookup"><span data-stu-id="3fab1-102">Getting Started</span></span>
<span data-ttu-id="3fab1-103">Utilizzando [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], è possibile utilizzare il [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] tecnologia di accesso SQL database esattamente come è possibile accedere a una raccolta in memoria.</span><span class="sxs-lookup"><span data-stu-id="3fab1-103">By using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you can use the [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] technology to access SQL databases just as you would access an in-memory collection.</span></span>  
  
 <span data-ttu-id="3fab1-104">Ad esempio, l'oggetto `nw` nel codice seguente viene creato per rappresentare il database `Northwind`, viene usata `Customers` come tabella di destinazione, le righe vengono filtrate in base a `Customers` residenti a `London` e viene selezionata una stringa da recuperare relativa a `CompanyName`.</span><span class="sxs-lookup"><span data-stu-id="3fab1-104">For example, the `nw` object in the following code is created to represent the `Northwind` database, the `Customers` table is targeted, the rows are filtered for `Customers` from `London`, and a string for `CompanyName` is selected for retrieval.</span></span>  
  
 <span data-ttu-id="3fab1-105">Quando viene eseguito il ciclo, viene recuperata la raccolta di valori `CompanyName`.</span><span class="sxs-lookup"><span data-stu-id="3fab1-105">When the loop is executed, the collection of `CompanyName` values is retrieved.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a><span data-ttu-id="3fab1-106">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="3fab1-106">Next Steps</span></span>  
 <span data-ttu-id="3fab1-107">Per alcuni esempi aggiuntivi, tra cui l'inserimento e aggiornamento, vedere [ciò che è possibile eseguire con LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/what-you-can-do-with-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="3fab1-107">For some additional examples, including inserting and updating, see [What You Can Do With LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/what-you-can-do-with-linq-to-sql.md).</span></span>  
  
 <span data-ttu-id="3fab1-108">Provare quindi a eseguire alcune procedure dettagliate ed esercitazioni per acquisire un'esperienza pratica relativa all'utilizzo di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3fab1-108">Next, try some walkthroughs and tutorials to have a hands-on experience of using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="3fab1-109">Vedere [apprendimento tramite procedure dettagliate](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).</span><span class="sxs-lookup"><span data-stu-id="3fab1-109">See [Learning by Walkthroughs](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).</span></span>  
  
 <span data-ttu-id="3fab1-110">Infine, informazioni su come iniziare a autonomamente [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] progetto leggendo [passaggi tipici per l'utilizzo di LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="3fab1-110">Finally, learn how to get started on your own [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project by reading [Typical Steps for Using LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fab1-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fab1-111">See Also</span></span>  
 [<span data-ttu-id="3fab1-112">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="3fab1-112">LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="3fab1-113">Introduzione a LINQ</span><span class="sxs-lookup"><span data-stu-id="3fab1-113">Introduction to LINQ</span></span>](http://msdn.microsoft.com/library/24dddf19-12a0-4707-a4bc-eba4fa7f219e)  
 [<span data-ttu-id="3fab1-114">Modello a oggetti LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="3fab1-114">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
