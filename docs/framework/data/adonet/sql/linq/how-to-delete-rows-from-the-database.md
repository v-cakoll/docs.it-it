---
title: 'Procedura: eliminare righe dal database'
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
ms.assetid: 2144c99b-8055-4080-a5c6-1ea14335e2a3
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 2bf7a701831dd08803c7fff6455d6ec3898df363
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-delete-rows-from-the-database"></a><span data-ttu-id="864a0-102">Procedura: eliminare righe dal database</span><span class="sxs-lookup"><span data-stu-id="864a0-102">How to: Delete Rows From the Database</span></span>
<span data-ttu-id="864a0-103">È possibile eliminare righe in un database rimuovendo corrispondente [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] oggetti dall'insieme alla tabella correlata.</span><span class="sxs-lookup"><span data-stu-id="864a0-103">You can delete rows in a database by removing the corresponding [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] objects from their table-related collection.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="864a0-104">Converte le modifiche apportate alla SQL appropriate `DELETE` comandi.</span><span class="sxs-lookup"><span data-stu-id="864a0-104"> translates your changes to the appropriate SQL `DELETE` commands.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="864a0-105"> non supporta o non riconosce operazioni di eliminazione a catena.</span><span class="sxs-lookup"><span data-stu-id="864a0-105"> does not support or recognize cascade-delete operations.</span></span> <span data-ttu-id="864a0-106">Se si desidera eliminare una riga in una tabella contenente vincoli, è necessario effettuare una delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="864a0-106">If you want to delete a row in a table that has constraints against it, you must complete either of the following tasks:</span></span>  
  
-   <span data-ttu-id="864a0-107">Impostare la regola `ON DELETE CASCADE` nel vincolo di chiave esterna del database.</span><span class="sxs-lookup"><span data-stu-id="864a0-107">Set the `ON DELETE CASCADE` rule in the foreign-key constraint in the database.</span></span>  
  
-   <span data-ttu-id="864a0-108">Usare il codice personalizzato per eliminare prima gli oggetti figlio che impediscono l'eliminazione dell'oggetto padre.</span><span class="sxs-lookup"><span data-stu-id="864a0-108">Use your own code to first delete the child objects that prevent the parent object from being deleted.</span></span>  
  
 <span data-ttu-id="864a0-109">In caso contrario, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="864a0-109">Otherwise, an exception is thrown.</span></span> <span data-ttu-id="864a0-110">Vedere il secondo esempio di codice riportato più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="864a0-110">See the second code example later in this topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="864a0-111">È possibile eseguire l'override dei metodi predefiniti [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per le operazioni di database `Insert`, `Update`e `Delete`.</span><span class="sxs-lookup"><span data-stu-id="864a0-111">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="864a0-112">Per ulteriori informazioni, vedere [personalizzazione di operazioni di inserimento, aggiornamento ed eliminare](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="864a0-112">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="864a0-113">Gli sviluppatori che usano [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] possono adoperare [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per sviluppare stored procedure allo stesso scopo.</span><span class="sxs-lookup"><span data-stu-id="864a0-113">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to develop stored procedures for the same purpose.</span></span>  
  
 <span data-ttu-id="864a0-114">Per l'esecuzione dei passaggi seguenti si presuppone l'uso di un oggetto <xref:System.Data.Linq.DataContext> valido per la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="864a0-114">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="864a0-115">Per ulteriori informazioni, vedere [procedura: connettersi a un Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="864a0-115">For more information, see [How to: Connect to a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span></span>  
  
### <a name="to-delete-a-row-in-the-database"></a><span data-ttu-id="864a0-116">Per eliminare una riga dal database</span><span class="sxs-lookup"><span data-stu-id="864a0-116">To delete a row in the database</span></span>  
  
1.  <span data-ttu-id="864a0-117">Eseguire una query sul database per la riga da eliminare.</span><span class="sxs-lookup"><span data-stu-id="864a0-117">Query the database for the row to be deleted.</span></span>  
  
2.  <span data-ttu-id="864a0-118">Chiamare il metodo <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>.</span><span class="sxs-lookup"><span data-stu-id="864a0-118">Call the <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> method.</span></span>  
  
3.  <span data-ttu-id="864a0-119">Inviare le modifiche al database.</span><span class="sxs-lookup"><span data-stu-id="864a0-119">Submit the change to the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="864a0-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="864a0-120">Example</span></span>  
 <span data-ttu-id="864a0-121">Nel primo esempio di codice viene eseguita una query sul database per ottenere dettagli relativi all'ordine N. 11000, questi dettagli relativi all'ordine vengono contrassegnati per l'eliminazione e tali modifiche vengono inviate al database.</span><span class="sxs-lookup"><span data-stu-id="864a0-121">This first code example queries the database for order details that belong to Order #11000, marks these order details for deletion, and submits these changes to the database.</span></span>  
  
 [!code-csharp[System.Data.Linq.Table#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#3)]
 [!code-vb[System.Data.Linq.Table#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="864a0-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="864a0-122">Example</span></span>  
 <span data-ttu-id="864a0-123">Nel secondo esempio, l'obiettivo è l'eliminazione di un ordine (N. 10250).</span><span class="sxs-lookup"><span data-stu-id="864a0-123">In this second example, the objective is to remove an order (#10250).</span></span> <span data-ttu-id="864a0-124">Il codice esamina innanzitutto la tabella `OrderDetails` per verificare se l'ordine da eliminare dispone di elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="864a0-124">The code first examines the `OrderDetails` table to see whether the order to be removed has children there.</span></span> <span data-ttu-id="864a0-125">In tal caso, gli elementi figlio e successivamente l'ordine vengono contrassegnati per l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="864a0-125">If the order has children, first the children and then the order are marked for removal.</span></span> <span data-ttu-id="864a0-126">L'oggetto <xref:System.Data.Linq.DataContext> ordina correttamente le eliminazioni effettive in modo che i comandi di eliminazione inviati al database si attengano ai vincoli del database.</span><span class="sxs-lookup"><span data-stu-id="864a0-126">The <xref:System.Data.Linq.DataContext> puts the actual deletes in correct order so that delete commands sent to the database abide by the database constraints.</span></span>  
  
 [!code-csharp[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCascadeWorkaround/cs/Program.cs#1)]
 [!code-vb[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCascadeWorkaround/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="864a0-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="864a0-127">See Also</span></span>  
 [<span data-ttu-id="864a0-128">Procedura: gestire i conflitti di modifiche</span><span class="sxs-lookup"><span data-stu-id="864a0-128">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [<span data-ttu-id="864a0-129">Procedura: assegnare stored procedure per eseguire aggiornamenti, inserimenti ed eliminazioni (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="864a0-129">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
 [<span data-ttu-id="864a0-130">Creazione e invio di modifiche ai dati</span><span class="sxs-lookup"><span data-stu-id="864a0-130">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
