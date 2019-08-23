---
title: 'Procedura: Aggiornare righe nel database'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a2b5c90f-6cc3-4128-bfab-1db488d5af26
ms.openlocfilehash: 2819cd5d2533e8e289735c3df2b39df952968e66
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938726"
---
# <a name="how-to-update-rows-in-the-database"></a><span data-ttu-id="5eb0b-102">Procedura: Aggiornare righe nel database</span><span class="sxs-lookup"><span data-stu-id="5eb0b-102">How to: Update Rows in the Database</span></span>
<span data-ttu-id="5eb0b-103">È possibile aggiornare le righe in un database modificando i valori dei membri degli oggetti associati [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> alla raccolta e quindi inviando le modifiche al database.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-103">You can update rows in a database by modifying member values of the objects associated with the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> collection and then submitting the changes to the database.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="5eb0b-104">converte le modifiche nei comandi SQL `UPDATE` appropriati.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-104">translates your changes into the appropriate SQL `UPDATE` commands.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5eb0b-105">È possibile eseguire l'override dei metodi predefiniti [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per le operazioni di database `Insert`, `Update`e `Delete`.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-105">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="5eb0b-106">Per ulteriori informazioni, vedere [personalizzazione di operazioni di inserimento, aggiornamento ed eliminazione](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="5eb0b-106">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="5eb0b-107">Gli sviluppatori che utilizzano Visual Studio possono utilizzare il Object Relational Designer per sviluppare stored procedure allo stesso scopo.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-107">Developers using Visual Studio can use the Object Relational Designer to develop stored procedures for the same purpose.</span></span>  
  
 <span data-ttu-id="5eb0b-108">Per l'esecuzione dei passaggi seguenti si presuppone l'uso di un oggetto <xref:System.Data.Linq.DataContext> valido per la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-108">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="5eb0b-109">Per altre informazioni, vedere [Procedura: Connettersi a un database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="5eb0b-109">For more information, see [How to: Connect to a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span></span>  
  
### <a name="to-update-a-row-in-the-database"></a><span data-ttu-id="5eb0b-110">Per aggiornare una riga nel database</span><span class="sxs-lookup"><span data-stu-id="5eb0b-110">To update a row in the database</span></span>  
  
1. <span data-ttu-id="5eb0b-111">Eseguire una query sul database per la riga da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-111">Query the database for the row to be updated.</span></span>  
  
2. <span data-ttu-id="5eb0b-112">Apportare le modifiche desiderate ai valori del membro nell'oggetto [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] risultante.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-112">Make desired changes to member values in the resulting [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object.</span></span>  
  
3. <span data-ttu-id="5eb0b-113">Inviare le modifiche al database.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-113">Submit the changes to the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5eb0b-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="5eb0b-114">Example</span></span>  
 <span data-ttu-id="5eb0b-115">Nell'esempio di codice seguente viene eseguita una query sul database per l'ordine N. 11000, quindi vengono modificati i valori di `ShipName` e `ShipVia` nell'oggetto `Order` risultante.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-115">The following example queries the database for order #11000, and then changes the values of `ShipName` and `ShipVia` in the resulting `Order` object.</span></span> <span data-ttu-id="5eb0b-116">Infine le modifiche a questi valori del membro vengono inviate al database come modifiche nelle colonne `ShipName` e `ShipVia`.</span><span class="sxs-lookup"><span data-stu-id="5eb0b-116">Finally, the changes to these member values are submitted to the database as changes in the `ShipName` and `ShipVia` columns.</span></span>  
  
 [!code-csharp[System.Data.Linq.Table#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.Table#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="5eb0b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5eb0b-117">See also</span></span>

- [<span data-ttu-id="5eb0b-118">Procedura: Gestione dei conflitti di modifica</span><span class="sxs-lookup"><span data-stu-id="5eb0b-118">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [<span data-ttu-id="5eb0b-119">Procedura: Assegnare stored procedure per eseguire aggiornamenti, inserimenti ed eliminazioni (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="5eb0b-119">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [<span data-ttu-id="5eb0b-120">Creazione e invio di modifiche dei dati</span><span class="sxs-lookup"><span data-stu-id="5eb0b-120">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
