---
title: 'Procedura: aggiornare righe nel database'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a2b5c90f-6cc3-4128-bfab-1db488d5af26
caps.latest.revision: 3
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 4ca47fb5a522ebcab68544a538064aa5cc3d60d7
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-update-rows-in-the-database"></a><span data-ttu-id="31253-102">Procedura: aggiornare righe nel database</span><span class="sxs-lookup"><span data-stu-id="31253-102">How to: Update Rows in the Database</span></span>
<span data-ttu-id="31253-103">È possibile aggiornare righe in un database modificando i valori dei membri di oggetti associati il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> raccolta, quindi inviando le modifiche al database.</span><span class="sxs-lookup"><span data-stu-id="31253-103">You can update rows in a database by modifying member values of the objects associated with the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> collection and then submitting the changes to the database.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="31253-104"> traduce le modifiche in SQL appropriate `UPDATE` comandi.</span><span class="sxs-lookup"><span data-stu-id="31253-104"> translates your changes into the appropriate SQL `UPDATE` commands.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31253-105">È possibile eseguire l'override dei metodi predefiniti [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per le operazioni di database `Insert`, `Update`e `Delete`.</span><span class="sxs-lookup"><span data-stu-id="31253-105">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="31253-106">Per ulteriori informazioni, vedere [personalizzazione di operazioni di inserimento, aggiornamento ed eliminare](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="31253-106">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="31253-107">Gli sviluppatori che usano Visual Studio è possono utilizzare il [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per sviluppare stored procedure allo stesso scopo.</span><span class="sxs-lookup"><span data-stu-id="31253-107">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to develop stored procedures for the same purpose.</span></span>  
  
 <span data-ttu-id="31253-108">Per l'esecuzione dei passaggi seguenti si presuppone l'uso di un oggetto <xref:System.Data.Linq.DataContext> valido per la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="31253-108">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="31253-109">Per ulteriori informazioni, vedere [procedura: connettersi a un Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="31253-109">For more information, see [How to: Connect to a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span></span>  
  
### <a name="to-update-a-row-in-the-database"></a><span data-ttu-id="31253-110">Per aggiornare una riga nel database</span><span class="sxs-lookup"><span data-stu-id="31253-110">To update a row in the database</span></span>  
  
1.  <span data-ttu-id="31253-111">Eseguire una query sul database per la riga da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="31253-111">Query the database for the row to be updated.</span></span>  
  
2.  <span data-ttu-id="31253-112">Apportare le modifiche desiderate ai valori del membro nell'oggetto [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] risultante.</span><span class="sxs-lookup"><span data-stu-id="31253-112">Make desired changes to member values in the resulting [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object.</span></span>  
  
3.  <span data-ttu-id="31253-113">Inviare le modifiche al database.</span><span class="sxs-lookup"><span data-stu-id="31253-113">Submit the changes to the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31253-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="31253-114">Example</span></span>  
 <span data-ttu-id="31253-115">Nell'esempio di codice seguente viene eseguita una query sul database per l'ordine N. 11000, quindi vengono modificati i valori di `ShipName` e `ShipVia` nell'oggetto `Order` risultante.</span><span class="sxs-lookup"><span data-stu-id="31253-115">The following example queries the database for order #11000, and then changes the values of `ShipName` and `ShipVia` in the resulting `Order` object.</span></span> <span data-ttu-id="31253-116">Infine le modifiche a questi valori del membro vengono inviate al database come modifiche nelle colonne `ShipName` e `ShipVia`.</span><span class="sxs-lookup"><span data-stu-id="31253-116">Finally, the changes to these member values are submitted to the database as changes in the `ShipName` and `ShipVia` columns.</span></span>  
  
 [!code-csharp[System.Data.Linq.Table#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.Table#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="31253-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31253-117">See Also</span></span>  
 [<span data-ttu-id="31253-118">Procedura: gestire i conflitti di modifiche</span><span class="sxs-lookup"><span data-stu-id="31253-118">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [<span data-ttu-id="31253-119">Procedura: assegnare stored procedure per eseguire aggiornamenti, inserimenti ed eliminazioni (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="31253-119">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
 [<span data-ttu-id="31253-120">Creazione e invio di modifiche dei dati</span><span class="sxs-lookup"><span data-stu-id="31253-120">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
