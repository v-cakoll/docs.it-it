---
title: 'Procedura: aggiornare righe nel database'
description: Informazioni su come aggiornare le righe in un database modificando LINQ to SQL oggetti in una raccolta correlata a tabella. LINQ to SQL converte le aggiunte ai comandi di SQL UPDATE.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a2b5c90f-6cc3-4128-bfab-1db488d5af26
ms.openlocfilehash: f25efb91fb5a83fb1c7c109bd018c8210edaec8b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286339"
---
# <a name="how-to-update-rows-in-the-database"></a><span data-ttu-id="4ea8c-104">Procedura: aggiornare righe nel database</span><span class="sxs-lookup"><span data-stu-id="4ea8c-104">How to: Update Rows in the Database</span></span>

<span data-ttu-id="4ea8c-105">È possibile aggiornare le righe in un database modificando i valori dei membri degli oggetti associati alla [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> raccolta e quindi inviando le modifiche al database.</span><span class="sxs-lookup"><span data-stu-id="4ea8c-105">You can update rows in a database by modifying member values of the objects associated with the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> collection and then submitting the changes to the database.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="4ea8c-106">converte le modifiche nei comandi SQL appropriati `UPDATE` .</span><span class="sxs-lookup"><span data-stu-id="4ea8c-106">translates your changes into the appropriate SQL `UPDATE` commands.</span></span>

> [!NOTE]
> <span data-ttu-id="4ea8c-107">È possibile eseguire l'override dei metodi predefiniti [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per le operazioni di database `Insert`, `Update`e `Delete`.</span><span class="sxs-lookup"><span data-stu-id="4ea8c-107">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="4ea8c-108">Per ulteriori informazioni, vedere [personalizzazione di operazioni di inserimento, aggiornamento ed eliminazione](customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="4ea8c-108">For more information, see [Customizing Insert, Update, and Delete Operations](customizing-insert-update-and-delete-operations.md).</span></span>
>
> <span data-ttu-id="4ea8c-109">Gli sviluppatori che utilizzano Visual Studio possono utilizzare il Object Relational Designer per sviluppare stored procedure allo stesso scopo.</span><span class="sxs-lookup"><span data-stu-id="4ea8c-109">Developers using Visual Studio can use the Object Relational Designer to develop stored procedures for the same purpose.</span></span>

<span data-ttu-id="4ea8c-110">Per l'esecuzione dei passaggi seguenti si presuppone l'uso di un oggetto <xref:System.Data.Linq.DataContext> valido per la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="4ea8c-110">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="4ea8c-111">Per altre informazioni, vedere [procedura: connettersi a un database](how-to-connect-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="4ea8c-111">For more information, see [How to: Connect to a Database](how-to-connect-to-a-database.md).</span></span>

### <a name="to-update-a-row-in-the-database"></a><span data-ttu-id="4ea8c-112">Per aggiornare una riga nel database</span><span class="sxs-lookup"><span data-stu-id="4ea8c-112">To update a row in the database</span></span>

1. <span data-ttu-id="4ea8c-113">Eseguire una query sul database per la riga da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="4ea8c-113">Query the database for the row to be updated.</span></span>

2. <span data-ttu-id="4ea8c-114">Apportare le modifiche desiderate ai valori del membro nell'oggetto [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] risultante.</span><span class="sxs-lookup"><span data-stu-id="4ea8c-114">Make desired changes to member values in the resulting [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object.</span></span>

3. <span data-ttu-id="4ea8c-115">Inviare le modifiche al database.</span><span class="sxs-lookup"><span data-stu-id="4ea8c-115">Submit the changes to the database.</span></span>

## <a name="example"></a><span data-ttu-id="4ea8c-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="4ea8c-116">Example</span></span>

<span data-ttu-id="4ea8c-117">Nell'esempio di codice seguente viene eseguita una query sul database per l'ordine N. 11000, quindi vengono modificati i valori di `ShipName` e `ShipVia` nell'oggetto `Order` risultante.</span><span class="sxs-lookup"><span data-stu-id="4ea8c-117">The following example queries the database for order #11000, and then changes the values of `ShipName` and `ShipVia` in the resulting `Order` object.</span></span> <span data-ttu-id="4ea8c-118">Infine le modifiche a questi valori del membro vengono inviate al database come modifiche nelle colonne `ShipName` e `ShipVia`.</span><span class="sxs-lookup"><span data-stu-id="4ea8c-118">Finally, the changes to these member values are submitted to the database as changes in the `ShipName` and `ShipVia` columns.</span></span>

[!code-csharp[System.Data.Linq.Table#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#2)]
[!code-vb[System.Data.Linq.Table#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#2)]

## <a name="see-also"></a><span data-ttu-id="4ea8c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ea8c-119">See also</span></span>

- [<span data-ttu-id="4ea8c-120">Procedura: gestire i conflitti di modifiche</span><span class="sxs-lookup"><span data-stu-id="4ea8c-120">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
- [<span data-ttu-id="4ea8c-121">Procedura: Assegnare stored procedure per eseguire aggiornamenti, inserimenti ed eliminazioni (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="4ea8c-121">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [<span data-ttu-id="4ea8c-122">Creazione e invio di modifiche dei dati</span><span class="sxs-lookup"><span data-stu-id="4ea8c-122">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
