---
title: Ordinamento e applicazione di filtri ai dati
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fdd9c753-39df-48cd-9822-2781afe76200
ms.openlocfilehash: 0907aa2a66e1bf51fefc7bed8ea2612cc0c830fa
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203224"
---
# <a name="sorting-and-filtering-data"></a><span data-ttu-id="c0485-102">Ordinamento e applicazione di filtri ai dati</span><span class="sxs-lookup"><span data-stu-id="c0485-102">Sorting and Filtering Data</span></span>
<span data-ttu-id="c0485-103">In <xref:System.Data.DataView> sono disponibili diversi metodi di ordinamento e applicazione di filtri ai dati in una <xref:System.Data.DataTable>:</span><span class="sxs-lookup"><span data-stu-id="c0485-103">The <xref:System.Data.DataView> provides several ways of sorting and filtering data in a <xref:System.Data.DataTable>:</span></span>  
  
- <span data-ttu-id="c0485-104">La proprietà <xref:System.Data.DataView.Sort%2A> viene usata per specificare criteri di ordinamento basati su una o più colonne e includere i parametri ASC (ascendente) e DESC (discendente).</span><span class="sxs-lookup"><span data-stu-id="c0485-104">You can use the <xref:System.Data.DataView.Sort%2A> property to specify single or multiple column sort orders and include ASC (ascending) and DESC (descending) parameters.</span></span>  
  
- <span data-ttu-id="c0485-105">La proprietà <xref:System.Data.DataView.ApplyDefaultSort%2A> consente di creare automaticamente un criterio di ordinamento ascendente, basato sulla colonna o sulle colonne di chiave primaria della tabella.</span><span class="sxs-lookup"><span data-stu-id="c0485-105">You can use the <xref:System.Data.DataView.ApplyDefaultSort%2A> property to automatically create a sort order, in ascending order, based on the primary key column or columns of the table.</span></span> <span data-ttu-id="c0485-106"><xref:System.Data.DataView.ApplyDefaultSort%2A>si applica solo quando la proprietà **Sort** è un riferimento null o una stringa vuota e quando la tabella contiene una chiave primaria definita.</span><span class="sxs-lookup"><span data-stu-id="c0485-106"><xref:System.Data.DataView.ApplyDefaultSort%2A> only applies when the **Sort** property is a null reference or an empty string, and when the table has a primary key defined.</span></span>  
  
- <span data-ttu-id="c0485-107">La proprietà <xref:System.Data.DataView.RowFilter%2A> consente di specificare subset di righe sulla base dei relativi valori di colonna.</span><span class="sxs-lookup"><span data-stu-id="c0485-107">You can use the <xref:System.Data.DataView.RowFilter%2A> property to specify subsets of rows based on their column values.</span></span> <span data-ttu-id="c0485-108">Per informazioni dettagliate sulle espressioni valide per la proprietà **RowFilter** , vedere le informazioni di riferimento <xref:System.Data.DataColumn.Expression%2A> per la proprietà <xref:System.Data.DataColumn> della classe.</span><span class="sxs-lookup"><span data-stu-id="c0485-108">For details about valid expressions for the **RowFilter** property, see the reference information for the <xref:System.Data.DataColumn.Expression%2A> property of the <xref:System.Data.DataColumn> class.</span></span>  
  
     <span data-ttu-id="c0485-109">Se si desidera restituire i risultati di una particolare query sui dati, anziché fornire una visualizzazione dinamica di un subset di dati, utilizzare i <xref:System.Data.DataView.Find%2A> metodi o <xref:System.Data.DataView.FindRows%2A> del **DataView** per ottenere prestazioni ottimali anziché impostare  **Proprietà RowFilter** .</span><span class="sxs-lookup"><span data-stu-id="c0485-109">If you want to return the results of a particular query on the data, as opposed to providing a dynamic view of a subset of the data, use the <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> methods of the **DataView** to achieve best performance rather than setting the **RowFilter** property.</span></span> <span data-ttu-id="c0485-110">Impostando la proprietà **RowFilter** , viene ricompilato l'indice per i dati, aggiungendo un sovraccarico all'applicazione e diminuendo le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="c0485-110">Setting the **RowFilter** property rebuilds the index for the data, adding overhead to your application and decreasing performance.</span></span> <span data-ttu-id="c0485-111">È consigliabile usare la proprietà **RowFilter** in un'applicazione con associazione a dati in cui un controllo associato Visualizza i risultati filtrati.</span><span class="sxs-lookup"><span data-stu-id="c0485-111">The **RowFilter** property is best used in a data-bound application where a bound control displays filtered results.</span></span> <span data-ttu-id="c0485-112">I metodi **Find** e **FindRows** sfruttano l'indice corrente senza richiedere la ricompilazione dell'indice.</span><span class="sxs-lookup"><span data-stu-id="c0485-112">The **Find** and **FindRows** methods leverage the current index without requiring the index to be rebuilt.</span></span> <span data-ttu-id="c0485-113">Per ulteriori informazioni sui metodi **Find** e **FindRows** , vedere [ricerca di righe](finding-rows.md).</span><span class="sxs-lookup"><span data-stu-id="c0485-113">For more information about the **Find** and **FindRows** methods, see [Finding Rows](finding-rows.md).</span></span>  
  
- <span data-ttu-id="c0485-114">La proprietà <xref:System.Data.DataView.RowStateFilter%2A> consente di specificare le versioni di riga da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="c0485-114">You can use the <xref:System.Data.DataView.RowStateFilter%2A> property to specify which row versions to view.</span></span> <span data-ttu-id="c0485-115">Il **DataView** gestisce in modo implicito la versione di riga da esporre a seconda del tipo di **RowState** della riga sottostante.</span><span class="sxs-lookup"><span data-stu-id="c0485-115">The **DataView** implicitly manages which row version to expose depending upon the **RowState** of the underlying row.</span></span> <span data-ttu-id="c0485-116">Se, ad esempio, **RowStateFilter** è impostato su **DataViewRowState. Deleted**, il **DataView** espone la versione di riga **originale** di tutte le righe **eliminate** perché non è disponibile una versione di riga **corrente** .</span><span class="sxs-lookup"><span data-stu-id="c0485-116">For example, if the **RowStateFilter** is set to **DataViewRowState.Deleted**, the **DataView** exposes the **Original** row version of all **Deleted** rows because there is no **Current** row version.</span></span> <span data-ttu-id="c0485-117">È possibile determinare la versione di riga di una riga esposta tramite la proprietà **rowversion** dell'oggetto **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="c0485-117">You can determine which row version of a row is being exposed by using the **RowVersion** property of the **DataRowView**.</span></span>  
  
     <span data-ttu-id="c0485-118">Nella tabella seguente vengono illustrate le opzioni per **DataViewRowState**.</span><span class="sxs-lookup"><span data-stu-id="c0485-118">The following table shows the options for **DataViewRowState**.</span></span>  
  
    |<span data-ttu-id="c0485-119">Opzioni di DataViewRowState</span><span class="sxs-lookup"><span data-stu-id="c0485-119">DataViewRowState options</span></span>|<span data-ttu-id="c0485-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c0485-120">Description</span></span>|  
    |------------------------------|-----------------|  
    |<span data-ttu-id="c0485-121">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="c0485-121">**CurrentRows**</span></span>|<span data-ttu-id="c0485-122">La versione di riga **corrente** di tutte le righe non **modificate**, **aggiunte**e **modificate** .</span><span class="sxs-lookup"><span data-stu-id="c0485-122">The **Current** row version of all **Unchanged**, **Added**, and **Modified** rows.</span></span> <span data-ttu-id="c0485-123">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c0485-123">This is the default.</span></span>|  
    |<span data-ttu-id="c0485-124">**Aggiunto**</span><span class="sxs-lookup"><span data-stu-id="c0485-124">**Added**</span></span>|<span data-ttu-id="c0485-125">Versione di riga **corrente** di tutte le righe **aggiunte** .</span><span class="sxs-lookup"><span data-stu-id="c0485-125">The **Current** row version of all **Added** rows.</span></span>|  
    |<span data-ttu-id="c0485-126">**Eliminato**</span><span class="sxs-lookup"><span data-stu-id="c0485-126">**Deleted**</span></span>|<span data-ttu-id="c0485-127">Versione di riga **originale** di tutte le righe eliminate.</span><span class="sxs-lookup"><span data-stu-id="c0485-127">The **Original** row version of all **Deleted** rows.</span></span>|  
    |<span data-ttu-id="c0485-128">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="c0485-128">**ModifiedCurrent**</span></span>|<span data-ttu-id="c0485-129">Versione di riga **corrente** di tutte le righe **modificate** .</span><span class="sxs-lookup"><span data-stu-id="c0485-129">The **Current** row version of all **Modified** rows.</span></span>|  
    |<span data-ttu-id="c0485-130">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="c0485-130">**ModifiedOriginal**</span></span>|<span data-ttu-id="c0485-131">Versione di riga **originale** di tutte le righe **modificate** .</span><span class="sxs-lookup"><span data-stu-id="c0485-131">The **Original** row version of all **Modified** rows.</span></span>|  
    |<span data-ttu-id="c0485-132">**None**</span><span class="sxs-lookup"><span data-stu-id="c0485-132">**None**</span></span>|<span data-ttu-id="c0485-133">Nessuna riga.</span><span class="sxs-lookup"><span data-stu-id="c0485-133">No rows.</span></span>|  
    |<span data-ttu-id="c0485-134">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="c0485-134">**OriginalRows**</span></span>|<span data-ttu-id="c0485-135">Versione di riga **originale** di tutte le righe non **modificate**, **modificate**ed **eliminate** .</span><span class="sxs-lookup"><span data-stu-id="c0485-135">The **Original** row version of all **Unchanged**, **Modified**, and **Deleted** rows.</span></span>|  
    |<span data-ttu-id="c0485-136">**Invariato**</span><span class="sxs-lookup"><span data-stu-id="c0485-136">**Unchanged**</span></span>|<span data-ttu-id="c0485-137">Versione di riga **corrente** di tutte le righe non **modificate** .</span><span class="sxs-lookup"><span data-stu-id="c0485-137">The **Current** row version of all **Unchanged** rows.</span></span>|  
  
 <span data-ttu-id="c0485-138">Per altre informazioni sugli Stati delle righe e sulle versioni delle righe, vedere Stati di riga [e versioni](row-states-and-row-versions.md)di riga.</span><span class="sxs-lookup"><span data-stu-id="c0485-138">For more information about row states and row versions, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="c0485-139">Nell'esempio di codice seguente viene creata una visualizzazione in cui vengono mostrati tutti i prodotti il cui numero di unità disponibili in magazzino è inferiore o uguale al livello di riordinamento. I prodotti vengono ordinati prima in base all'identificatore del fornitore, quindi in base al nome del prodotto.</span><span class="sxs-lookup"><span data-stu-id="c0485-139">The following code example creates a view that shows all the products where the number of units in stock is less than or equal to the reorder level, sorted first by supplier ID and then by product name.</span></span>  
  
```vb  
Dim prodView As DataView = New DataView(prodDS.Tables("Products"), _  
   "UnitsInStock <= ReorderLevel", _  
   "SupplierID, ProductName", _  
   DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView prodView = new DataView(prodDS.Tables["Products"],  
   "UnitsInStock <= ReorderLevel",  
   "SupplierID, ProductName",  
   DataViewRowState.CurrentRows);  
```  
  
## <a name="see-also"></a><span data-ttu-id="c0485-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0485-140">See also</span></span>

- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="c0485-141">DataView</span><span class="sxs-lookup"><span data-stu-id="c0485-141">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="c0485-142">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="c0485-142">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
