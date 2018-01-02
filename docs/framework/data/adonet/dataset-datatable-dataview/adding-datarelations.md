---
title: Aggiunta di oggetti DataRelation
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
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 9741f44b68e1cac8c464338f556979d682d9e128
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="adding-datarelations"></a><span data-ttu-id="16944-102">Aggiunta di oggetti DataRelation</span><span class="sxs-lookup"><span data-stu-id="16944-102">Adding DataRelations</span></span>
<span data-ttu-id="16944-103">In un <xref:System.Data.DataSet> contenente più oggetti <xref:System.Data.DataTable> è possibile usare gli oggetti <xref:System.Data.DataRelation> per creare relazioni tra le tabelle, navigare tra di esse e restituire le righe padre o figlio da una tabella correlata.</span><span class="sxs-lookup"><span data-stu-id="16944-103">In a <xref:System.Data.DataSet> with multiple <xref:System.Data.DataTable> objects, you can use <xref:System.Data.DataRelation> objects to relate one table to another, to navigate through the tables, and to return child or parent rows from a related table.</span></span>  
  
 <span data-ttu-id="16944-104">Gli argomenti necessari per creare un **DataRelation** sono un nome per il **DataRelation** creato e una matrice di uno o più <xref:System.Data.DataColumn> i riferimenti alle colonne che fungono da padre e figlio colonne nella relazione.</span><span class="sxs-lookup"><span data-stu-id="16944-104">The arguments required to create a **DataRelation** are a name for the **DataRelation** being created, and an array of one or more <xref:System.Data.DataColumn> references to the columns that serve as the parent and child columns in the relationship.</span></span> <span data-ttu-id="16944-105">Dopo aver creato un **DataRelation**, è possibile utilizzare per navigare tra le tabelle e recuperare i valori.</span><span class="sxs-lookup"><span data-stu-id="16944-105">After you have created a **DataRelation**, you can use it to navigate between tables and to retrieve values.</span></span>  
  
 <span data-ttu-id="16944-106">Aggiunta di un **DataRelation** per un <xref:System.Data.DataSet> aggiunge, per impostazione predefinita, un <xref:System.Data.UniqueConstraint> alla tabella padre e un <xref:System.Data.ForeignKeyConstraint> alla tabella figlio.</span><span class="sxs-lookup"><span data-stu-id="16944-106">Adding a **DataRelation** to a <xref:System.Data.DataSet> adds, by default, a <xref:System.Data.UniqueConstraint> to the parent table and a <xref:System.Data.ForeignKeyConstraint> to the child table.</span></span> <span data-ttu-id="16944-107">Per ulteriori informazioni sui vincoli predefiniti, vedere [vincoli DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="16944-107">For more information about these default constraints, see [DataTable Constraints](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="16944-108">L'esempio di codice seguente crea un **DataRelation** utilizzando due <xref:System.Data.DataTable> gli oggetti in un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="16944-108">The following code example creates a **DataRelation** using two <xref:System.Data.DataTable> objects in a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="16944-109">Ogni <xref:System.Data.DataTable> contiene una colonna denominata **CustID**, che funge da collegamento tra i due <xref:System.Data.DataTable> oggetti.</span><span class="sxs-lookup"><span data-stu-id="16944-109">Each <xref:System.Data.DataTable> contains a column named **CustID**, which serves as a link between the two <xref:System.Data.DataTable> objects.</span></span> <span data-ttu-id="16944-110">Nell'esempio viene aggiunto un singolo **DataRelation** per il **relazioni** insieme il <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="16944-110">The example adds a single **DataRelation** to the **Relations** collection of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="16944-111">Il primo argomento dell'esempio specifica il nome del **DataRelation** da creare.</span><span class="sxs-lookup"><span data-stu-id="16944-111">The first argument in the example specifies the name of the **DataRelation** being created.</span></span> <span data-ttu-id="16944-112">Il secondo argomento imposta l'elemento padre **DataColumn** e il terzo argomento imposta l'elemento figlio **DataColumn**.</span><span class="sxs-lookup"><span data-stu-id="16944-112">The second argument sets the parent **DataColumn** and the third argument sets the child **DataColumn**.</span></span>  
  
```vb  
customerOrders.Relations.Add("CustOrders", _  
  customerOrders.Tables("Customers").Columns("CustID"), _  
  customerOrders.Tables("Orders").Columns("CustID"))  
```  
  
```csharp  
customerOrders.Relations.Add("CustOrders",  
  customerOrders.Tables["Customers"].Columns["CustID"],  
  customerOrders.Tables["Orders"].Columns["CustID"]);  
```  
  
 <span data-ttu-id="16944-113">A **DataRelation** dispone anche di un **Nested** proprietà che, se impostato su **true**, fa sì che le righe della tabella figlio all'interno della riga associata nella tabella padre Quando scritte come elementi XML tramite <xref:System.Data.DataSet.WriteXml%2A> .</span><span class="sxs-lookup"><span data-stu-id="16944-113">A **DataRelation** also has a **Nested** property which, when set to **true**, causes the rows from the child table to be nested within the associated row from the parent table when written as XML elements using <xref:System.Data.DataSet.WriteXml%2A> .</span></span> <span data-ttu-id="16944-114">Per altre informazioni, vedere [Uso di XML in un set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="16944-114">For more information, see [Using XML in a DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16944-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16944-115">See Also</span></span>  
 [<span data-ttu-id="16944-116">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="16944-116">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="16944-117">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="16944-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
