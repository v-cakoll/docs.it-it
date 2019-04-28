---
title: 'Procedura: Inserire righe nel database'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 44d99680-69c7-4879-a732-f6771b334211
ms.openlocfilehash: cb2319d51e0518114a04eea2fc7ab6b5a836b7ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61903071"
---
# <a name="how-to-insert-rows-into-the-database"></a><span data-ttu-id="b74b1-102">Procedura: Inserire righe nel database</span><span class="sxs-lookup"><span data-stu-id="b74b1-102">How to: Insert Rows Into the Database</span></span>
<span data-ttu-id="b74b1-103">Per inserire righe in un database mediante l'aggiunta di oggetti associati [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> raccolta e quindi inviare le modifiche al database.</span><span class="sxs-lookup"><span data-stu-id="b74b1-103">You insert rows into a database by adding objects to the associated [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> collection and then submitting the changes to the database.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="b74b1-104">le modifiche vengono convertite in SQL appropriate `INSERT` comandi.</span><span class="sxs-lookup"><span data-stu-id="b74b1-104">translates your changes into the appropriate SQL `INSERT` commands.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b74b1-105">È possibile eseguire l'override dei metodi predefiniti [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per le operazioni di database `Insert`, `Update`e `Delete`.</span><span class="sxs-lookup"><span data-stu-id="b74b1-105">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="b74b1-106">Per altre informazioni, vedere [personalizzazione di operazioni di inserimento, aggiornamento ed eliminare](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="b74b1-106">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="b74b1-107">Gli sviluppatori che usano Visual Studio è possono usare il [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per sviluppare stored procedure per lo stesso scopo.</span><span class="sxs-lookup"><span data-stu-id="b74b1-107">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to develop stored procedures for the same purpose.</span></span>  
  
 <span data-ttu-id="b74b1-108">Per l'esecuzione dei passaggi seguenti si presuppone l'uso di un oggetto <xref:System.Data.Linq.DataContext> valido per la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="b74b1-108">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="b74b1-109">Per altre informazioni, vedere [Procedura: Connettersi a un Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="b74b1-109">For more information, see [How to: Connect to a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span></span>  
  
### <a name="to-insert-a-row-into-the-database"></a><span data-ttu-id="b74b1-110">Per inserire una riga nel database</span><span class="sxs-lookup"><span data-stu-id="b74b1-110">To insert a row into the database</span></span>  
  
1. <span data-ttu-id="b74b1-111">Creare un nuovo oggetto contenente i dati della colonna da inviare.</span><span class="sxs-lookup"><span data-stu-id="b74b1-111">Create a new object that includes the column data to be submitted.</span></span>  
  
2. <span data-ttu-id="b74b1-112">Aggiungere il nuovo oggetto per il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` raccolta associata alla tabella di destinazione nel database.</span><span class="sxs-lookup"><span data-stu-id="b74b1-112">Add the new object to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` collection associated with the target table in the database.</span></span>  
  
3. <span data-ttu-id="b74b1-113">Inviare le modifiche al database.</span><span class="sxs-lookup"><span data-stu-id="b74b1-113">Submit the change to the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b74b1-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="b74b1-114">Example</span></span>  
 <span data-ttu-id="b74b1-115">L'esempio di codice seguente consente di creare un nuovo oggetto di tipo `Order` e di popolarlo con i valori corretti.</span><span class="sxs-lookup"><span data-stu-id="b74b1-115">The following code example creates a new object of type `Order` and populates it with appropriate values.</span></span> <span data-ttu-id="b74b1-116">Il nuovo oggetto viene quindi aggiunto alla raccolta `Order`.</span><span class="sxs-lookup"><span data-stu-id="b74b1-116">It then adds the new object to the `Order` collection.</span></span> <span data-ttu-id="b74b1-117">Infine viene inviata la modifica al database come una nuova riga nella tabella `Orders`.</span><span class="sxs-lookup"><span data-stu-id="b74b1-117">Finally, it submits the change to the database as a new row in the `Orders` table.</span></span>  
  
 [!code-csharp[System.Data.Linq.Table#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.Table#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b74b1-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b74b1-118">See also</span></span>

- [<span data-ttu-id="b74b1-119">Procedura: Gestire i conflitti di modifiche</span><span class="sxs-lookup"><span data-stu-id="b74b1-119">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [<span data-ttu-id="b74b1-120">Metodi DataContext (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="b74b1-120">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="b74b1-121">Procedura: Assegnare stored procedure per eseguire aggiornamenti, inserimenti ed eliminazioni (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="b74b1-121">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [<span data-ttu-id="b74b1-122">Creazione e invio di modifiche dei dati</span><span class="sxs-lookup"><span data-stu-id="b74b1-122">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
