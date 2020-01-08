---
title: Operazioni eseguibili con LINQ to SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 061d98b2-baa7-4336-8ad2-c14de8134d91
ms.openlocfilehash: e84047843aff4044c75ba1b971a9e2f061e2e8d6
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634001"
---
# <a name="what-you-can-do-with-linq-to-sql"></a><span data-ttu-id="8b6f0-102">Operazioni eseguibili con LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="8b6f0-102">What You Can Do With LINQ to SQL</span></span>
<span data-ttu-id="8b6f0-103">In[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sono supportare tutte le funzionalità principali usate dagli sviluppatori SQL.</span><span class="sxs-lookup"><span data-stu-id="8b6f0-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supports all the key capabilities you would expect as a SQL developer.</span></span> <span data-ttu-id="8b6f0-104">È possibile creare query per ottenere informazioni ed eseguire operazioni di inserimento, aggiornamento ed eliminazione di dati dalle tabelle.</span><span class="sxs-lookup"><span data-stu-id="8b6f0-104">You can query for information, and insert, update, and delete information from tables.</span></span>  
  
## <a name="selecting"></a><span data-ttu-id="8b6f0-105">Selezione</span><span class="sxs-lookup"><span data-stu-id="8b6f0-105">Selecting</span></span>  
 <span data-ttu-id="8b6f0-106">Per ottenere la selezione (*proiezione*) è sufficiente scrivere una query LINQ nel proprio linguaggio di programmazione e quindi eseguire la query per recuperare i risultati.</span><span class="sxs-lookup"><span data-stu-id="8b6f0-106">Selecting (*projection*) is achieved by just writing a LINQ query in your own programming language, and then executing that query to retrieve the results.</span></span> <span data-ttu-id="8b6f0-107">In[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tutte le operazioni indispensabili vengono convertite nelle operazioni SQL necessarie con cui si ha dimestichezza.</span><span class="sxs-lookup"><span data-stu-id="8b6f0-107">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] itself translates all the necessary operations into the necessary SQL operations that you are familiar with.</span></span> <span data-ttu-id="8b6f0-108">Per altre informazioni, vedere [LINQ to SQL](index.md).</span><span class="sxs-lookup"><span data-stu-id="8b6f0-108">For more information, see [LINQ to SQL](index.md).</span></span>  
  
 <span data-ttu-id="8b6f0-109">Nell'esempio seguente i nomi di società dei clienti dell'area londinese vengono recuperati e visualizzati nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="8b6f0-109">In the following example, the company names of customers from London are retrieved and displayed in the console window.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="inserting"></a><span data-ttu-id="8b6f0-110">Inserimento</span><span class="sxs-lookup"><span data-stu-id="8b6f0-110">Inserting</span></span>  
 <span data-ttu-id="8b6f0-111">Per eseguire un'operazione `Insert`SQL, aggiungere semplicemente oggetti al modello a oggetti creato e chiamare <xref:System.Data.Linq.DataContext.SubmitChanges%2A> su <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="8b6f0-111">To execute a SQL `Insert`, just add objects to the object model you have created, and call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 <span data-ttu-id="8b6f0-112">Nell'esempio seguente vengono aggiunti un nuovo cliente e informazioni sul cliente alla tabella `Customers` usando <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>.</span><span class="sxs-lookup"><span data-stu-id="8b6f0-112">In the following example, a new customer and information about the customer is added to the `Customers` table by using <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#2)]
 [!code-vb[DLinqGettingStarted#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#2)]  
  
## <a name="updating"></a><span data-ttu-id="8b6f0-113">Aggiornamento</span><span class="sxs-lookup"><span data-stu-id="8b6f0-113">Updating</span></span>  
 <span data-ttu-id="8b6f0-114">Per eseguire un'operazione `Update` per una voce del database, recuperare innanzitutto tale voce e modificarla direttamente nel modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="8b6f0-114">To `Update` a database entry, first retrieve the item and edit it directly in the object model.</span></span> <span data-ttu-id="8b6f0-115">Dopo avere modificato l'oggetto, chiamare <xref:System.Data.Linq.DataContext.SubmitChanges%2A> su <xref:System.Data.Linq.DataContext> per aggiornare il database.</span><span class="sxs-lookup"><span data-stu-id="8b6f0-115">After you have modified the object, call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext> to update the database.</span></span>  
  
 <span data-ttu-id="8b6f0-116">Nell'esempio seguente vengono recuperati tutti i clienti dell'area londinese.</span><span class="sxs-lookup"><span data-stu-id="8b6f0-116">In the following example, all customers who are from London are retrieved.</span></span> <span data-ttu-id="8b6f0-117">Il nome della città viene quindi modificato da "London" in "London - Metro",</span><span class="sxs-lookup"><span data-stu-id="8b6f0-117">Then the name of the city is changed from "London" to "London - Metro".</span></span> <span data-ttu-id="8b6f0-118">infine viene chiamato <xref:System.Data.Linq.DataContext.SubmitChanges%2A> per inviare le modifiche al database.</span><span class="sxs-lookup"><span data-stu-id="8b6f0-118">Finally, <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called to send the changes to the database.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#3)]
 [!code-vb[DLinqGettingStarted#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#3)]  
  
## <a name="deleting"></a><span data-ttu-id="8b6f0-119">Eliminazione</span><span class="sxs-lookup"><span data-stu-id="8b6f0-119">Deleting</span></span>  
 <span data-ttu-id="8b6f0-120">Per eseguire un'operazione `Delete` per un elemento, rimuovere l'elemento dalla raccolta a cui appartiene, quindi chiamare <xref:System.Data.Linq.DataContext.SubmitChanges%2A> su <xref:System.Data.Linq.DataContext> per eseguire il commit della modifica.</span><span class="sxs-lookup"><span data-stu-id="8b6f0-120">To `Delete` an item, remove the item from the collection to which it belongs, and then call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext> to commit the change.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8b6f0-121">In[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non vengono riconosciute le operazioni di eliminazione a sovrapposizione.</span><span class="sxs-lookup"><span data-stu-id="8b6f0-121">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not recognize cascade-delete operations.</span></span> <span data-ttu-id="8b6f0-122">Se si desidera eliminare una riga in una tabella che contiene vincoli, vedere [procedura: eliminare righe dal database](how-to-delete-rows-from-the-database.md).</span><span class="sxs-lookup"><span data-stu-id="8b6f0-122">If you want to delete a row in a table that has constraints against it, see [How to: Delete Rows From the Database](how-to-delete-rows-from-the-database.md).</span></span>  
  
 <span data-ttu-id="8b6f0-123">Nell'esempio seguente il cliente con il codice `CustomerID``98128` viene recuperato dal database.</span><span class="sxs-lookup"><span data-stu-id="8b6f0-123">In the following example, the customer who has `CustomerID` of `98128` is retrieved from the database.</span></span> <span data-ttu-id="8b6f0-124">Quindi, dopo la conferma che la riga del cliente è stata recuperata, viene chiamato <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> per rimuovere quell'oggetto dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="8b6f0-124">Then, after confirming that the customer row was retrieved, <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> is called to remove that object from the collection.</span></span> <span data-ttu-id="8b6f0-125">Infine viene chiamato <xref:System.Data.Linq.DataContext.SubmitChanges%2A> per inoltrare l'operazione di eliminazione al database.</span><span class="sxs-lookup"><span data-stu-id="8b6f0-125">Finally, <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called to forward the deletion to the database.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#4)]
 [!code-vb[DLinqGettingStarted#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="8b6f0-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b6f0-126">See also</span></span>

- [<span data-ttu-id="8b6f0-127">Guida per programmatori</span><span class="sxs-lookup"><span data-stu-id="8b6f0-127">Programming Guide</span></span>](programming-guide.md)
- [<span data-ttu-id="8b6f0-128">Modello a oggetti LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="8b6f0-128">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="8b6f0-129">Introduzione</span><span class="sxs-lookup"><span data-stu-id="8b6f0-129">Getting Started</span></span>](getting-started.md)
