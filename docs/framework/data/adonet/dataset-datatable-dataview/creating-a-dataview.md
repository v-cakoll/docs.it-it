---
title: Creazione di un oggetto DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 3e1c31dac458594eee70ddd99469aca7cf63b848
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785479"
---
# <a name="creating-a-dataview"></a><span data-ttu-id="bcd2e-102">Creazione di un oggetto DataView</span><span class="sxs-lookup"><span data-stu-id="bcd2e-102">Creating a DataView</span></span>
<span data-ttu-id="bcd2e-103">Per creare un <xref:System.Data.DataView>, sono disponibili due modalità.</span><span class="sxs-lookup"><span data-stu-id="bcd2e-103">There are two ways to create a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="bcd2e-104">È possibile usare il costruttore **DataView** oppure è possibile creare un riferimento alla <xref:System.Data.DataTable.DefaultView%2A> proprietà di. <xref:System.Data.DataTable></span><span class="sxs-lookup"><span data-stu-id="bcd2e-104">You can use the **DataView** constructor, or you can create a reference to the <xref:System.Data.DataTable.DefaultView%2A> property of the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="bcd2e-105">Il costruttore **DataView** può essere vuoto oppure può assumere un **oggetto DataTable** come singolo argomento oppure un **DataTable** insieme a criteri di filtro, criteri di ordinamento e un filtro di stato della riga.</span><span class="sxs-lookup"><span data-stu-id="bcd2e-105">The **DataView** constructor can be empty, or it can take either a **DataTable** as a single argument, or a **DataTable** along with filter criteria, sort criteria, and a row state filter.</span></span> <span data-ttu-id="bcd2e-106">Per ulteriori informazioni sugli argomenti aggiuntivi disponibili per l'utilizzo con **DataView**, vedere [ordinamento e filtro dei dati](sorting-and-filtering-data.md).</span><span class="sxs-lookup"><span data-stu-id="bcd2e-106">For more information about the additional arguments available for use with the **DataView**, see [Sorting and Filtering Data](sorting-and-filtering-data.md).</span></span>  
  
 <span data-ttu-id="bcd2e-107">Poiché l'indice di un oggetto **DataView** viene compilato sia quando viene creato il **DataView** , sia quando viene modificata una delle proprietà **Sort**, **RowFilter**o **RowStateFilter** , si ottengono le migliori prestazioni fornendo eventuali iniziali ordinare o filtrare i criteri come argomenti del costruttore quando si crea il **DataView**.</span><span class="sxs-lookup"><span data-stu-id="bcd2e-107">Because the index for a **DataView** is built both when the **DataView** is created, and when any of the **Sort**, **RowFilter**, or **RowStateFilter** properties are modified, you achieve best performance by supplying any initial sort order or filtering criteria as constructor arguments when you create the **DataView**.</span></span> <span data-ttu-id="bcd2e-108">La creazione di un oggetto **DataView** senza specificare criteri di ordinamento o di filtro e l'impostazione delle proprietà **Sort**, **RowFilter**o **RowStateFilter** in un secondo momento comporta la compilazione dell'indice almeno due volte: una volta quando il **DataView** è creato e di nuovo quando una delle proprietà di ordinamento o filtro viene modificata.</span><span class="sxs-lookup"><span data-stu-id="bcd2e-108">Creating a **DataView** without specifying sort or filter criteria and then setting the **Sort**, **RowFilter**, or **RowStateFilter** properties later causes the index to be built at least twice: once when the **DataView** is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="bcd2e-109">Si noti che se si crea un **DataView** usando il costruttore che non accetta argomenti, non sarà possibile usare il **DataView** fino a quando non viene impostata la proprietà **Table** .</span><span class="sxs-lookup"><span data-stu-id="bcd2e-109">Note that if you create a **DataView** using the constructor that does not take any arguments, you will not be able to use the **DataView** until you have set the **Table** property.</span></span>  
  
 <span data-ttu-id="bcd2e-110">Nell'esempio di codice seguente viene illustrato come creare un **DataView** utilizzando il costruttore **DataView** .</span><span class="sxs-lookup"><span data-stu-id="bcd2e-110">The following code example demonstrates how to create a **DataView** using the **DataView** constructor.</span></span> <span data-ttu-id="bcd2e-111">Insieme alla **DataTable**vengono forniti un **RowFilter**, una colonna di **ordinamento** e **DataViewRowState** .</span><span class="sxs-lookup"><span data-stu-id="bcd2e-111">A **RowFilter**, **Sort** column, and **DataViewRowState** are supplied along with the **DataTable**.</span></span>  
  
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
  
 <span data-ttu-id="bcd2e-112">Nell'esempio di codice riportato di seguito viene illustrato come ottenere un riferimento al **DataView** predefinito di una **DataTable** utilizzando la proprietà **DefaultView** della tabella.</span><span class="sxs-lookup"><span data-stu-id="bcd2e-112">The following code example demonstrates how to obtain a reference to the default **DataView** of a **DataTable** using the **DefaultView** property of the table.</span></span>  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a><span data-ttu-id="bcd2e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bcd2e-113">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="bcd2e-114">DataView</span><span class="sxs-lookup"><span data-stu-id="bcd2e-114">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="bcd2e-115">Ordinamento e applicazione di filtri ai dati</span><span class="sxs-lookup"><span data-stu-id="bcd2e-115">Sorting and Filtering Data</span></span>](sorting-and-filtering-data.md)
- [<span data-ttu-id="bcd2e-116">DataTable</span><span class="sxs-lookup"><span data-stu-id="bcd2e-116">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="bcd2e-117">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bcd2e-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
