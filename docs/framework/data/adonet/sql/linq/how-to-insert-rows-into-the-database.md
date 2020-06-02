---
title: 'Procedura: inserire righe nel database'
description: Informazioni su come inserire righe in un database aggiungendo LINQ to SQL oggetti a una raccolta correlata a una tabella. LINQ to SQL converte le aggiunte ai comandi SQL INSERT.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 44d99680-69c7-4879-a732-f6771b334211
ms.openlocfilehash: 39eee6edf59d2adb7de41efd88899050fbe69fd8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286352"
---
# <a name="how-to-insert-rows-into-the-database"></a><span data-ttu-id="7b1c3-104">Procedura: inserire righe nel database</span><span class="sxs-lookup"><span data-stu-id="7b1c3-104">How to: Insert Rows Into the Database</span></span>

<span data-ttu-id="7b1c3-105">Per inserire righe in un database, è necessario aggiungere oggetti alla [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> raccolta associata e quindi inviare le modifiche al database.</span><span class="sxs-lookup"><span data-stu-id="7b1c3-105">You insert rows into a database by adding objects to the associated [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> collection and then submitting the changes to the database.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="7b1c3-106">converte le modifiche nei comandi SQL appropriati `INSERT` .</span><span class="sxs-lookup"><span data-stu-id="7b1c3-106">translates your changes into the appropriate SQL `INSERT` commands.</span></span>

> [!NOTE]
> <span data-ttu-id="7b1c3-107">È possibile eseguire l'override dei metodi predefiniti [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per le operazioni di database `Insert`, `Update`e `Delete`.</span><span class="sxs-lookup"><span data-stu-id="7b1c3-107">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="7b1c3-108">Per ulteriori informazioni, vedere [personalizzazione di operazioni di inserimento, aggiornamento ed eliminazione](customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="7b1c3-108">For more information, see [Customizing Insert, Update, and Delete Operations](customizing-insert-update-and-delete-operations.md).</span></span>
>
> <span data-ttu-id="7b1c3-109">Gli sviluppatori che utilizzano Visual Studio possono utilizzare il Object Relational Designer per sviluppare stored procedure allo stesso scopo.</span><span class="sxs-lookup"><span data-stu-id="7b1c3-109">Developers using Visual Studio can use the Object Relational Designer to develop stored procedures for the same purpose.</span></span>

<span data-ttu-id="7b1c3-110">Per l'esecuzione dei passaggi seguenti si presuppone l'uso di un oggetto <xref:System.Data.Linq.DataContext> valido per la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="7b1c3-110">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="7b1c3-111">Per altre informazioni, vedere [procedura: connettersi a un database](how-to-connect-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="7b1c3-111">For more information, see [How to: Connect to a Database](how-to-connect-to-a-database.md).</span></span>

### <a name="to-insert-a-row-into-the-database"></a><span data-ttu-id="7b1c3-112">Per inserire una riga nel database</span><span class="sxs-lookup"><span data-stu-id="7b1c3-112">To insert a row into the database</span></span>

1. <span data-ttu-id="7b1c3-113">Creare un nuovo oggetto contenente i dati della colonna da inviare.</span><span class="sxs-lookup"><span data-stu-id="7b1c3-113">Create a new object that includes the column data to be submitted.</span></span>

2. <span data-ttu-id="7b1c3-114">Aggiungere il nuovo oggetto alla [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` raccolta associata alla tabella di destinazione nel database.</span><span class="sxs-lookup"><span data-stu-id="7b1c3-114">Add the new object to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` collection associated with the target table in the database.</span></span>

3. <span data-ttu-id="7b1c3-115">Inviare le modifiche al database.</span><span class="sxs-lookup"><span data-stu-id="7b1c3-115">Submit the change to the database.</span></span>

## <a name="example"></a><span data-ttu-id="7b1c3-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="7b1c3-116">Example</span></span>

<span data-ttu-id="7b1c3-117">L'esempio di codice seguente consente di creare un nuovo oggetto di tipo `Order` e di popolarlo con i valori corretti.</span><span class="sxs-lookup"><span data-stu-id="7b1c3-117">The following code example creates a new object of type `Order` and populates it with appropriate values.</span></span> <span data-ttu-id="7b1c3-118">Il nuovo oggetto viene quindi aggiunto alla raccolta `Order`.</span><span class="sxs-lookup"><span data-stu-id="7b1c3-118">It then adds the new object to the `Order` collection.</span></span> <span data-ttu-id="7b1c3-119">Infine viene inviata la modifica al database come una nuova riga nella tabella `Orders`.</span><span class="sxs-lookup"><span data-stu-id="7b1c3-119">Finally, it submits the change to the database as a new row in the `Orders` table.</span></span>

[!code-csharp[System.Data.Linq.Table#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#1)]
[!code-vb[System.Data.Linq.Table#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="7b1c3-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b1c3-120">See also</span></span>

- [<span data-ttu-id="7b1c3-121">Procedura: gestire i conflitti di modifiche</span><span class="sxs-lookup"><span data-stu-id="7b1c3-121">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
- [<span data-ttu-id="7b1c3-122">Metodi DataContext (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="7b1c3-122">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="7b1c3-123">Procedura: Assegnare stored procedure per eseguire aggiornamenti, inserimenti ed eliminazioni (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="7b1c3-123">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [<span data-ttu-id="7b1c3-124">Creazione e invio di modifiche dei dati</span><span class="sxs-lookup"><span data-stu-id="7b1c3-124">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
