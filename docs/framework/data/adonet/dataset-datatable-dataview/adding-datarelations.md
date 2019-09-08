---
title: Aggiunta di oggetti DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: 8157d296636d0f8661a35af35de561f5cc49c30b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784815"
---
# <a name="adding-datarelations"></a><span data-ttu-id="b3112-102">Aggiunta di oggetti DataRelation</span><span class="sxs-lookup"><span data-stu-id="b3112-102">Adding DataRelations</span></span>
<span data-ttu-id="b3112-103">In un <xref:System.Data.DataSet> contenente più oggetti <xref:System.Data.DataTable> è possibile usare gli oggetti <xref:System.Data.DataRelation> per creare relazioni tra le tabelle, navigare tra di esse e restituire le righe padre o figlio da una tabella correlata.</span><span class="sxs-lookup"><span data-stu-id="b3112-103">In a <xref:System.Data.DataSet> with multiple <xref:System.Data.DataTable> objects, you can use <xref:System.Data.DataRelation> objects to relate one table to another, to navigate through the tables, and to return child or parent rows from a related table.</span></span>  
  
 <span data-ttu-id="b3112-104">Gli argomenti necessari per creare un oggetto **DataRelation** sono un nome per l'oggetto **DataRelation** creato e una matrice di uno o più <xref:System.Data.DataColumn> riferimenti alle colonne utilizzate come colonne padre e figlio nella relazione.</span><span class="sxs-lookup"><span data-stu-id="b3112-104">The arguments required to create a **DataRelation** are a name for the **DataRelation** being created, and an array of one or more <xref:System.Data.DataColumn> references to the columns that serve as the parent and child columns in the relationship.</span></span> <span data-ttu-id="b3112-105">Dopo aver creato un oggetto **DataRelation**, è possibile utilizzarlo per spostarsi tra le tabelle e recuperare i valori.</span><span class="sxs-lookup"><span data-stu-id="b3112-105">After you have created a **DataRelation**, you can use it to navigate between tables and to retrieve values.</span></span>  
  
 <span data-ttu-id="b3112-106">L'aggiunta di un oggetto **DataRelation** a un oggetto <xref:System.Data.DataSet> aggiunge, <xref:System.Data.UniqueConstraint> per impostazione predefinita, un oggetto <xref:System.Data.ForeignKeyConstraint> alla tabella padre e un oggetto alla tabella figlio.</span><span class="sxs-lookup"><span data-stu-id="b3112-106">Adding a **DataRelation** to a <xref:System.Data.DataSet> adds, by default, a <xref:System.Data.UniqueConstraint> to the parent table and a <xref:System.Data.ForeignKeyConstraint> to the child table.</span></span> <span data-ttu-id="b3112-107">Per ulteriori informazioni su questi vincoli predefiniti, vedere [vincoli DataTable](datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="b3112-107">For more information about these default constraints, see [DataTable Constraints](datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="b3112-108">Nell'esempio di codice seguente viene creato un oggetto **DataRelation** utilizzando <xref:System.Data.DataTable> due <xref:System.Data.DataSet>oggetti in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="b3112-108">The following code example creates a **DataRelation** using two <xref:System.Data.DataTable> objects in a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="b3112-109">Ogni <xref:System.Data.DataTable> contiene una colonna denominata **CustID**, che funge da collegamento tra i due <xref:System.Data.DataTable> oggetti.</span><span class="sxs-lookup"><span data-stu-id="b3112-109">Each <xref:System.Data.DataTable> contains a column named **CustID**, which serves as a link between the two <xref:System.Data.DataTable> objects.</span></span> <span data-ttu-id="b3112-110">Nell'esempio viene aggiunto un singolo oggetto **DataRelation** alla raccolta **Relations** dell'oggetto <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="b3112-110">The example adds a single **DataRelation** to the **Relations** collection of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="b3112-111">Il primo argomento nell'esempio specifica il nome dell'oggetto **DataRelation** da creare.</span><span class="sxs-lookup"><span data-stu-id="b3112-111">The first argument in the example specifies the name of the **DataRelation** being created.</span></span> <span data-ttu-id="b3112-112">Il secondo argomento imposta la **DataColumn** padre e il terzo argomento imposta la **DataColumn**figlio.</span><span class="sxs-lookup"><span data-stu-id="b3112-112">The second argument sets the parent **DataColumn** and the third argument sets the child **DataColumn**.</span></span>  
  
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
  
 <span data-ttu-id="b3112-113">Un oggetto **DataRelation** dispone inoltre di una proprietà **annidata** che, se impostata su **true**, determina l'annidamento delle righe della tabella figlio all'interno della riga associata della tabella padre quando vengono scritti come <xref:System.Data.DataSet.WriteXml%2A> elementi XML mediante.</span><span class="sxs-lookup"><span data-stu-id="b3112-113">A **DataRelation** also has a **Nested** property which, when set to **true**, causes the rows from the child table to be nested within the associated row from the parent table when written as XML elements using <xref:System.Data.DataSet.WriteXml%2A> .</span></span> <span data-ttu-id="b3112-114">Per altre informazioni, vedere [Uso di XML in un set di dati](using-xml-in-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="b3112-114">For more information, see [Using XML in a DataSet](using-xml-in-a-dataset.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3112-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3112-115">See also</span></span>

- [<span data-ttu-id="b3112-116">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="b3112-116">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="b3112-117">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b3112-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
