---
title: Esplorazione di oggetti DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5e673f4-9b44-45ae-aaea-c504d1cc5d3e
ms.openlocfilehash: c46007fb86a76405fd99d6e943779238d6885aa8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761428"
---
# <a name="navigating-datarelations"></a><span data-ttu-id="b563b-102">Esplorazione di oggetti DataRelation</span><span class="sxs-lookup"><span data-stu-id="b563b-102">Navigating DataRelations</span></span>
<span data-ttu-id="b563b-103">Una delle funzioni principali di un oggetto <xref:System.Data.DataRelation> è di consentire la navigazione da una <xref:System.Data.DataTable> all'altra all'interno di un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="b563b-103">One of the primary functions of a <xref:System.Data.DataRelation> is to allow navigation from one <xref:System.Data.DataTable> to another within a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="b563b-104">In questo modo è possibile recuperare tutti gli <xref:System.Data.DataRow> gli oggetti in uno **DataTable** quando viene specificato un singolo **DataRow** da un processo di **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="b563b-104">This allows you to retrieve all the related <xref:System.Data.DataRow> objects in one **DataTable** when given a single **DataRow** from a related **DataTable**.</span></span> <span data-ttu-id="b563b-105">Ad esempio, dopo aver stabilito un **DataRelation** tra una tabella di clienti e una tabella di ordini, è possibile recuperare tutte le righe di ordine per un particolare cliente usando **GetChildRows**.</span><span class="sxs-lookup"><span data-stu-id="b563b-105">For example, after establishing a **DataRelation** between a table of customers and a table of orders, you can retrieve all the order rows for a particular customer row using **GetChildRows**.</span></span>  
  
 <span data-ttu-id="b563b-106">L'esempio di codice seguente crea un **DataRelation** tra il **clienti** tabella e **ordini** tabella di un **DataSet** e restituisce tutti gli ordini per ogni cliente.</span><span class="sxs-lookup"><span data-stu-id="b563b-106">The following code example creates a **DataRelation** between the **Customers** table and the **Orders** table of a **DataSet** and returns all the orders for each customer.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/VB/source.vb#1)]  
  
 <span data-ttu-id="b563b-107">Nell'esempio successivo, basato su quello precedente, vengono correlate quattro tabelle e vengono esplorate tali relazioni.</span><span class="sxs-lookup"><span data-stu-id="b563b-107">The next example builds on the preceding example, relating four tables together and navigating those relationships.</span></span> <span data-ttu-id="b563b-108">Come nell'esempio precedente, **CustomerID** si riferisce il **clienti** tabella il **ordini** tabella.</span><span class="sxs-lookup"><span data-stu-id="b563b-108">As in the previous example, **CustomerID** relates the **Customers** table to the **Orders** table.</span></span> <span data-ttu-id="b563b-109">Per ogni cliente nel **clienti** tabella, tutte le righe figlio il **ordini** tabella dipendono, per restituire il numero di ordini di un determinato cliente e le relative **OrderID** valori.</span><span class="sxs-lookup"><span data-stu-id="b563b-109">For each customer in the **Customers** table, all the child rows in the **Orders** table are determined, in order to return the number of orders a particular customer has and their **OrderID** values.</span></span>  
  
 <span data-ttu-id="b563b-110">Nell'esempio espanso restituisce anche i valori di **OrderDetails** e **prodotti** tabelle.</span><span class="sxs-lookup"><span data-stu-id="b563b-110">The expanded example also returns the values from the **OrderDetails** and **Products** tables.</span></span> <span data-ttu-id="b563b-111">Il **ordini** tabella è correlata al **OrderDetails** tramite **OrderID** per determinare per ogni ordine del cliente, quali prodotti e le quantità ordinate.</span><span class="sxs-lookup"><span data-stu-id="b563b-111">The **Orders** table is related to the **OrderDetails** table using **OrderID** to determine, for each customer order, what products and quantities were ordered.</span></span> <span data-ttu-id="b563b-112">Poiché il **OrderDetails** tabella contiene solo il **ProductID** di un prodotto ordinato, **OrderDetails** è correlata a **prodotti** utilizzando **ProductID** per restituire il **ProductName**.</span><span class="sxs-lookup"><span data-stu-id="b563b-112">Because the **OrderDetails** table only contains the **ProductID** of an ordered product, **OrderDetails** is related to **Products** using **ProductID** in order to return the **ProductName**.</span></span> <span data-ttu-id="b563b-113">In questo tipo di relazione di **prodotti** è la tabella padre e **Order Details** è la tabella figlio.</span><span class="sxs-lookup"><span data-stu-id="b563b-113">In this relation, the **Products** table is the parent and the **Order Details** table is the child.</span></span> <span data-ttu-id="b563b-114">Di conseguenza, quando si scorre il **OrderDetails** tabella **GetParentRow** viene chiamata per recuperare l'oggetto correlato **ProductName** valore.</span><span class="sxs-lookup"><span data-stu-id="b563b-114">As a result, when iterating through the **OrderDetails** table, **GetParentRow** is called to retrieve the related **ProductName** value.</span></span>  
  
 <span data-ttu-id="b563b-115">Si noti che quando il **DataRelation** viene creato per il **clienti** e **ordini** tabelle, viene specificato alcun valore per il **createConstraints**flag (il valore predefinito è **true**).</span><span class="sxs-lookup"><span data-stu-id="b563b-115">Notice that when the **DataRelation** is created for the **Customers** and **Orders** tables, no value is specified for the **createConstraints** flag (the default is **true**).</span></span> <span data-ttu-id="b563b-116">Si presuppone che tutte le righe il **ordini** tabella hanno un **CustomerID** valore esistente nell'elemento padre **clienti** tabella.</span><span class="sxs-lookup"><span data-stu-id="b563b-116">This assumes that all the rows in the **Orders** table have a **CustomerID** value that exists in the parent **Customers** table.</span></span> <span data-ttu-id="b563b-117">Se un **CustomerID** esiste nel **ordini** tabella che non esiste nel **clienti** tabella, una <xref:System.Data.ForeignKeyConstraint> viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="b563b-117">If a **CustomerID** exists in the **Orders** table that does not exist in the **Customers** table, a <xref:System.Data.ForeignKeyConstraint> causes an exception to be thrown.</span></span>  
  
 <span data-ttu-id="b563b-118">Quando la colonna figlio può contenere valori che non contiene la colonna padre, impostare il **createConstraints** flag **false** quando si aggiunge il **DataRelation**.</span><span class="sxs-lookup"><span data-stu-id="b563b-118">When the child column might contain values that the parent column does not contain, set the **createConstraints** flag to **false** when adding the **DataRelation**.</span></span> <span data-ttu-id="b563b-119">Nell'esempio di **createConstraints** flag è impostato su **false** per il **DataRelation** tra il **ordini** tabella e il  **OrderDetails** tabella.</span><span class="sxs-lookup"><span data-stu-id="b563b-119">In the example, the **createConstraints** flag is set to **false** for the **DataRelation** between the **Orders** table and the **OrderDetails** table.</span></span> <span data-ttu-id="b563b-120">Questo consente all'applicazione restituire tutti i record di **OrderDetails** tabella e solo un subset di record dal **ordini** tabella senza generare un'eccezione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b563b-120">This enables the application to return all the records from the **OrderDetails** table and only a subset of records from the **Orders** table without generating a run-time exception.</span></span> <span data-ttu-id="b563b-121">Nell'esempio espanso viene generato un output con il seguente formato.</span><span class="sxs-lookup"><span data-stu-id="b563b-121">The expanded sample generates output in the following format.</span></span>  
  
```  
Customer ID: NORTS  
  Order ID: 10517  
        Order Date: 4/24/1997 12:00:00 AM  
           Product: Filo Mix  
          Quantity: 6  
           Product: Raclette Courdavault  
          Quantity: 4  
           Product: Outback Lager  
          Quantity: 6  
  Order ID: 11057  
        Order Date: 4/29/1998 12:00:00 AM  
           Product: Outback Lager  
          Quantity: 3  
```  
  
 <span data-ttu-id="b563b-122">L'esempio di codice seguente è un esempio ampliato in cui i valori di **OrderDetails** e **prodotti** vengono restituite le tabelle, solo un subset dei record del **ordini**tabella restituita.</span><span class="sxs-lookup"><span data-stu-id="b563b-122">The following code example is an expanded sample where the values from the **OrderDetails** and **Products** tables are returned, with only a subset of the records in the **Orders** table being returned.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b563b-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b563b-123">See Also</span></span>  
 [<span data-ttu-id="b563b-124">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="b563b-124">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="b563b-125">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="b563b-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
