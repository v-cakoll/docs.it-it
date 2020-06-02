---
title: 'Procedura: eliminare righe dal database'
description: Informazioni su come eliminare righe in un database rimuovendo LINQ to SQL oggetti da una raccolta correlata a una tabella. LINQ to SQL converte le eliminazioni in comandi SQL DELETE.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2144c99b-8055-4080-a5c6-1ea14335e2a3
ms.openlocfilehash: d08621e834961e1db9312cac36bd2e69133142b5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286391"
---
# <a name="how-to-delete-rows-from-the-database"></a><span data-ttu-id="879f8-104">Procedura: eliminare righe dal database</span><span class="sxs-lookup"><span data-stu-id="879f8-104">How to: Delete Rows From the Database</span></span>

<span data-ttu-id="879f8-105">È possibile eliminare righe in un database rimuovendo gli [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] oggetti corrispondenti dalla raccolta relativa alla tabella.</span><span class="sxs-lookup"><span data-stu-id="879f8-105">You can delete rows in a database by removing the corresponding [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] objects from their table-related collection.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="879f8-106">converte le modifiche apportate ai comandi SQL appropriati `DELETE` .</span><span class="sxs-lookup"><span data-stu-id="879f8-106">translates your changes to the appropriate SQL `DELETE` commands.</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="879f8-107">non supporta o non riconosce operazioni di eliminazione a catena.</span><span class="sxs-lookup"><span data-stu-id="879f8-107">does not support or recognize cascade-delete operations.</span></span> <span data-ttu-id="879f8-108">Se si desidera eliminare una riga in una tabella contenente vincoli, è necessario effettuare una delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="879f8-108">If you want to delete a row in a table that has constraints against it, you must complete either of the following tasks:</span></span>

- <span data-ttu-id="879f8-109">Impostare la regola `ON DELETE CASCADE` nel vincolo di chiave esterna del database.</span><span class="sxs-lookup"><span data-stu-id="879f8-109">Set the `ON DELETE CASCADE` rule in the foreign-key constraint in the database.</span></span>

- <span data-ttu-id="879f8-110">Usare il codice personalizzato per eliminare prima gli oggetti figlio che impediscono l'eliminazione dell'oggetto padre.</span><span class="sxs-lookup"><span data-stu-id="879f8-110">Use your own code to first delete the child objects that prevent the parent object from being deleted.</span></span>

 <span data-ttu-id="879f8-111">In caso contrario, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="879f8-111">Otherwise, an exception is thrown.</span></span> <span data-ttu-id="879f8-112">Vedere il secondo esempio di codice riportato più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="879f8-112">See the second code example later in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="879f8-113">È possibile eseguire l'override dei metodi predefiniti [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per le operazioni di database `Insert`, `Update`e `Delete`.</span><span class="sxs-lookup"><span data-stu-id="879f8-113">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="879f8-114">Per ulteriori informazioni, vedere [personalizzazione di operazioni di inserimento, aggiornamento ed eliminazione](customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="879f8-114">For more information, see [Customizing Insert, Update, and Delete Operations](customizing-insert-update-and-delete-operations.md).</span></span>
>
> <span data-ttu-id="879f8-115">Gli sviluppatori che utilizzano Visual Studio possono utilizzare il Object Relational Designer per sviluppare stored procedure allo stesso scopo.</span><span class="sxs-lookup"><span data-stu-id="879f8-115">Developers using Visual Studio can use the Object Relational Designer to develop stored procedures for the same purpose.</span></span>

<span data-ttu-id="879f8-116">Per l'esecuzione dei passaggi seguenti si presuppone l'uso di un oggetto <xref:System.Data.Linq.DataContext> valido per la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="879f8-116">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="879f8-117">Per altre informazioni, vedere [procedura: connettersi a un database](how-to-connect-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="879f8-117">For more information, see [How to: Connect to a Database](how-to-connect-to-a-database.md).</span></span>

### <a name="to-delete-a-row-in-the-database"></a><span data-ttu-id="879f8-118">Per eliminare una riga dal database</span><span class="sxs-lookup"><span data-stu-id="879f8-118">To delete a row in the database</span></span>

1. <span data-ttu-id="879f8-119">Eseguire una query sul database per la riga da eliminare.</span><span class="sxs-lookup"><span data-stu-id="879f8-119">Query the database for the row to be deleted.</span></span>

2. <span data-ttu-id="879f8-120">Chiamare il metodo <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> .</span><span class="sxs-lookup"><span data-stu-id="879f8-120">Call the <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> method.</span></span>

3. <span data-ttu-id="879f8-121">Inviare le modifiche al database.</span><span class="sxs-lookup"><span data-stu-id="879f8-121">Submit the change to the database.</span></span>

## <a name="example"></a><span data-ttu-id="879f8-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="879f8-122">Example</span></span>

<span data-ttu-id="879f8-123">Nel primo esempio di codice viene eseguita una query sul database per ottenere dettagli relativi all'ordine N. 11000, questi dettagli relativi all'ordine vengono contrassegnati per l'eliminazione e tali modifiche vengono inviate al database.</span><span class="sxs-lookup"><span data-stu-id="879f8-123">This first code example queries the database for order details that belong to Order #11000, marks these order details for deletion, and submits these changes to the database.</span></span>

[!code-csharp[System.Data.Linq.Table#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#3)]
[!code-vb[System.Data.Linq.Table#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#3)]

## <a name="example"></a><span data-ttu-id="879f8-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="879f8-124">Example</span></span>

<span data-ttu-id="879f8-125">Nel secondo esempio, l'obiettivo è l'eliminazione di un ordine (N. 10250).</span><span class="sxs-lookup"><span data-stu-id="879f8-125">In this second example, the objective is to remove an order (#10250).</span></span> <span data-ttu-id="879f8-126">Il codice esamina innanzitutto la tabella `OrderDetails` per verificare se l'ordine da eliminare dispone di elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="879f8-126">The code first examines the `OrderDetails` table to see whether the order to be removed has children there.</span></span> <span data-ttu-id="879f8-127">In tal caso, gli elementi figlio e successivamente l'ordine vengono contrassegnati per l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="879f8-127">If the order has children, first the children and then the order are marked for removal.</span></span> <span data-ttu-id="879f8-128">L'oggetto <xref:System.Data.Linq.DataContext> ordina correttamente le eliminazioni effettive in modo che i comandi di eliminazione inviati al database si attengano ai vincoli del database.</span><span class="sxs-lookup"><span data-stu-id="879f8-128">The <xref:System.Data.Linq.DataContext> puts the actual deletes in correct order so that delete commands sent to the database abide by the database constraints.</span></span>

[!code-csharp[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCascadeWorkaround/cs/Program.cs#1)]
[!code-vb[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCascadeWorkaround/vb/Module1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="879f8-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="879f8-129">See also</span></span>

- [<span data-ttu-id="879f8-130">Procedura: gestire i conflitti di modifiche</span><span class="sxs-lookup"><span data-stu-id="879f8-130">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
- [<span data-ttu-id="879f8-131">Procedura: Assegnare stored procedure per eseguire aggiornamenti, inserimenti ed eliminazioni (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="879f8-131">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [<span data-ttu-id="879f8-132">Creazione e invio di modifiche dei dati</span><span class="sxs-lookup"><span data-stu-id="879f8-132">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
