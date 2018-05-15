---
title: Creazione di un oggetto DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: d118f97e425782dbdf89c7e5d1eccd4d371b419c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="creating-a-dataview"></a><span data-ttu-id="127be-102">Creazione di un oggetto DataView</span><span class="sxs-lookup"><span data-stu-id="127be-102">Creating a DataView</span></span>
<span data-ttu-id="127be-103">Per creare un <xref:System.Data.DataView>, sono disponibili due modalità.</span><span class="sxs-lookup"><span data-stu-id="127be-103">There are two ways to create a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="127be-104">È possibile utilizzare il **DataView** costruttore, oppure è possibile creare un riferimento al <xref:System.Data.DataTable.DefaultView%2A> proprietà del <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="127be-104">You can use the **DataView** constructor, or you can create a reference to the <xref:System.Data.DataTable.DefaultView%2A> property of the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="127be-105">Il **DataView** costruttore può essere vuoto oppure può accettare un **DataTable** come argomento singolo, o un **DataTable** insieme ai criteri di filtro, criteri di ordinamento e una riga filtro di stato.</span><span class="sxs-lookup"><span data-stu-id="127be-105">The **DataView** constructor can be empty, or it can take either a **DataTable** as a single argument, or a **DataTable** along with filter criteria, sort criteria, and a row state filter.</span></span> <span data-ttu-id="127be-106">Per ulteriori informazioni sugli argomenti aggiuntivi per l'utilizzo con il **DataView**, vedere [ordinamento e filtraggio dei dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).</span><span class="sxs-lookup"><span data-stu-id="127be-106">For more information about the additional arguments available for use with the **DataView**, see [Sorting and Filtering Data](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).</span></span>  
  
 <span data-ttu-id="127be-107">Poiché l'indice per un **DataView** viene compilato sia quando la **DataView** viene creato e quando un il **ordinamento**, **RowFilter**, o  **RowStateFilter** si modificano le proprietà, per ottenere prestazioni ottimali di fornire qualsiasi tipo di ordinamento iniziale o criteri di filtro come argomenti del costruttore quando si crea il **DataView**.</span><span class="sxs-lookup"><span data-stu-id="127be-107">Because the index for a **DataView** is built both when the **DataView** is created, and when any of the **Sort**, **RowFilter**, or **RowStateFilter** properties are modified, you achieve best performance by supplying any initial sort order or filtering criteria as constructor arguments when you create the **DataView**.</span></span> <span data-ttu-id="127be-108">Creazione di un **DataView** senza specificare i criteri di ordinamento o filtro e quindi impostando la **ordinamento**, **RowFilter**, o **RowStateFilter** le proprietà in un secondo momento fa sì che l'indice verrà compilato almeno due volte: una volta quando il **DataView** viene creato e nuovamente quando le proprietà di ordinamento o filtro vengono modificate.</span><span class="sxs-lookup"><span data-stu-id="127be-108">Creating a **DataView** without specifying sort or filter criteria and then setting the **Sort**, **RowFilter**, or **RowStateFilter** properties later causes the index to be built at least twice: once when the **DataView** is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="127be-109">Si noti che se si crea un **DataView** utilizzando il costruttore che non accetta alcun argomento, non sarà in grado di utilizzare il **DataView** fino a quando non è stato impostato il **tabella** proprietà .</span><span class="sxs-lookup"><span data-stu-id="127be-109">Note that if you create a **DataView** using the constructor that does not take any arguments, you will not be able to use the **DataView** until you have set the **Table** property.</span></span>  
  
 <span data-ttu-id="127be-110">Esempio di codice riportato di seguito viene illustrato come creare un **DataView** utilizzando il **DataView** costruttore.</span><span class="sxs-lookup"><span data-stu-id="127be-110">The following code example demonstrates how to create a **DataView** using the **DataView** constructor.</span></span> <span data-ttu-id="127be-111">Oggetto **RowFilter**, **ordinamento** colonna, e **DataViewRowState** vengono forniti con il **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="127be-111">A **RowFilter**, **Sort** column, and **DataViewRowState** are supplied along with the **DataTable**.</span></span>  
  
```vb  
Dim custDV As DataView = New DataView(custDS.Tables("Customers"), _  
    "Country = 'USA'", _  
    "ContactName", _  
    DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView custDV = new DataView(custDS.Tables["Customers"],   
    "Country = 'USA'",   
    "ContactName",   
    DataViewRowState.CurrentRows);  
```  
  
 <span data-ttu-id="127be-112">Esempio di codice riportato di seguito viene illustrato come ottenere un riferimento all'impostazione predefinita **DataView** di un **DataTable** utilizzando il **DefaultView** proprietà della tabella.</span><span class="sxs-lookup"><span data-stu-id="127be-112">The following code example demonstrates how to obtain a reference to the default **DataView** of a **DataTable** using the **DefaultView** property of the table.</span></span>  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a><span data-ttu-id="127be-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="127be-113">See Also</span></span>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [<span data-ttu-id="127be-114">DataView</span><span class="sxs-lookup"><span data-stu-id="127be-114">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="127be-115">Ordinamento e applicazione di filtri ai dati</span><span class="sxs-lookup"><span data-stu-id="127be-115">Sorting and Filtering Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 [<span data-ttu-id="127be-116">DataTable</span><span class="sxs-lookup"><span data-stu-id="127be-116">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="127be-117">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="127be-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
