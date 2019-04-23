---
title: Creazione di un dataset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 57629d8f-393e-4677-8b83-29ffde27f5fc
ms.openlocfilehash: d2d17056e6dcd29ef9b5c5e8c3024a32fce32bd5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59118183"
---
# <a name="creating-a-dataset"></a><span data-ttu-id="656bf-102">Creazione di un dataset</span><span class="sxs-lookup"><span data-stu-id="656bf-102">Creating a DataSet</span></span>
<span data-ttu-id="656bf-103">È possibile creare un'istanza di un tipo<xref:System.Data.DataSet> chiamando il costruttore <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="656bf-103">You create an instance of a <xref:System.Data.DataSet> by calling the <xref:System.Data.DataSet> constructor.</span></span> <span data-ttu-id="656bf-104">Facoltativamente, specificare un nome di argomento.</span><span class="sxs-lookup"><span data-stu-id="656bf-104">Optionally specify a name argument.</span></span> <span data-ttu-id="656bf-105">Se non si specifica alcun nome per il tipo <xref:System.Data.DataSet>, verrà usato il nome "NewDataSet".</span><span class="sxs-lookup"><span data-stu-id="656bf-105">If you do not specify a name for the <xref:System.Data.DataSet>, the name is set to "NewDataSet".</span></span>  
  
 <span data-ttu-id="656bf-106">È inoltre possibile creare un nuovo tipo <xref:System.Data.DataSet> basato su un tipo <xref:System.Data.DataSet> esistente.</span><span class="sxs-lookup"><span data-stu-id="656bf-106">You can also create a new <xref:System.Data.DataSet> based on an existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="656bf-107">Il nuovo tipo <xref:System.Data.DataSet> può essere una copia esatta del <xref:System.Data.DataSet> esistente; un duplicato del tipo <xref:System.Data.DataSet> in cui viene copiata la struttura relazionale o lo schema ma in cui non è presente alcun dato proveniente dal <xref:System.Data.DataSet> esistente; oppure un subset del tipo <xref:System.Data.DataSet>, contenente solo le righe modificate del <xref:System.Data.DataSet> esistente usando il metodo <xref:System.Data.DataSet.GetChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="656bf-107">The new <xref:System.Data.DataSet> can be an exact copy of the existing <xref:System.Data.DataSet>; a clone of the <xref:System.Data.DataSet> that copies the relational structure or schema but that does not contain any of the data from the existing <xref:System.Data.DataSet>; or a subset of the <xref:System.Data.DataSet>, containing only the modified rows from the existing <xref:System.Data.DataSet> using the <xref:System.Data.DataSet.GetChanges%2A> method.</span></span> <span data-ttu-id="656bf-108">Per altre informazioni, vedere [copia di contenuti di DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/copying-dataset-contents.md).</span><span class="sxs-lookup"><span data-stu-id="656bf-108">For more information, see [Copying DataSet Contents](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/copying-dataset-contents.md).</span></span>  
  
 <span data-ttu-id="656bf-109">Nell'esempio di codice seguente viene illustrata la creazione di un'istanza di un tipo <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="656bf-109">The following code example demonstrates how to construct an instance of a <xref:System.Data.DataSet>.</span></span>  
  
```vb  
Dim customerOrders As DataSet = New DataSet("CustomerOrders")  
```  
  
```csharp  
DataSet customerOrders = new DataSet("CustomerOrders");  
```  
  
## <a name="see-also"></a><span data-ttu-id="656bf-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="656bf-110">See also</span></span>

- [<span data-ttu-id="656bf-111">Popolamento di un set di dati da un oggetto DataAdapter</span><span class="sxs-lookup"><span data-stu-id="656bf-111">Populating a DataSet from a DataAdapter</span></span>](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)
- [<span data-ttu-id="656bf-112">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="656bf-112">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="656bf-113">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="656bf-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
