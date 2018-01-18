---
title: Ordinamento e applicazione di filtri ai dati
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
ms.assetid: fdd9c753-39df-48cd-9822-2781afe76200
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 2411307623c714ae521d00dcffca05d3569a656e
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="sorting-and-filtering-data"></a><span data-ttu-id="bf7b4-102">Ordinamento e applicazione di filtri ai dati</span><span class="sxs-lookup"><span data-stu-id="bf7b4-102">Sorting and Filtering Data</span></span>
<span data-ttu-id="bf7b4-103">In <xref:System.Data.DataView> sono disponibili diversi metodi di ordinamento e applicazione di filtri ai dati in una <xref:System.Data.DataTable>:</span><span class="sxs-lookup"><span data-stu-id="bf7b4-103">The <xref:System.Data.DataView> provides several ways of sorting and filtering data in a <xref:System.Data.DataTable>:</span></span>  
  
-   <span data-ttu-id="bf7b4-104">La proprietà <xref:System.Data.DataView.Sort%2A> viene usata per specificare criteri di ordinamento basati su una o più colonne e includere i parametri ASC (ascendente) e DESC (discendente).</span><span class="sxs-lookup"><span data-stu-id="bf7b4-104">You can use the <xref:System.Data.DataView.Sort%2A> property to specify single or multiple column sort orders and include ASC (ascending) and DESC (descending) parameters.</span></span>  
  
-   <span data-ttu-id="bf7b4-105">La proprietà <xref:System.Data.DataView.ApplyDefaultSort%2A> consente di creare automaticamente un criterio di ordinamento ascendente, basato sulla colonna o sulle colonne di chiave primaria della tabella.</span><span class="sxs-lookup"><span data-stu-id="bf7b4-105">You can use the <xref:System.Data.DataView.ApplyDefaultSort%2A> property to automatically create a sort order, in ascending order, based on the primary key column or columns of the table.</span></span> <span data-ttu-id="bf7b4-106"><xref:System.Data.DataView.ApplyDefaultSort%2A>si applica solo quando il **ordinamento** proprietà è un riferimento null o una stringa vuota, e quando la tabella contiene una chiave primaria definita.</span><span class="sxs-lookup"><span data-stu-id="bf7b4-106"><xref:System.Data.DataView.ApplyDefaultSort%2A> only applies when the **Sort** property is a null reference or an empty string, and when the table has a primary key defined.</span></span>  
  
-   <span data-ttu-id="bf7b4-107">La proprietà <xref:System.Data.DataView.RowFilter%2A> consente di specificare subset di righe sulla base dei relativi valori di colonna.</span><span class="sxs-lookup"><span data-stu-id="bf7b4-107">You can use the <xref:System.Data.DataView.RowFilter%2A> property to specify subsets of rows based on their column values.</span></span> <span data-ttu-id="bf7b4-108">Per informazioni dettagliate sulle espressioni valide per il **RowFilter** proprietà, vedere le informazioni di riferimento per il <xref:System.Data.DataColumn.Expression%2A> proprietà del <xref:System.Data.DataColumn> classe.</span><span class="sxs-lookup"><span data-stu-id="bf7b4-108">For details about valid expressions for the **RowFilter** property, see the reference information for the <xref:System.Data.DataColumn.Expression%2A> property of the <xref:System.Data.DataColumn> class.</span></span>  
  
     <span data-ttu-id="bf7b4-109">Se si desidera restituire i risultati di una particolare query sui dati anziché fornire una visualizzazione dinamica di un subset dei dati, utilizzare il <xref:System.Data.DataView.Find%2A> o <xref:System.Data.DataView.FindRows%2A> metodi il **DataView** per ottenere prestazioni ottimali anziché l'impostazione di **RowFilter** proprietà.</span><span class="sxs-lookup"><span data-stu-id="bf7b4-109">If you want to return the results of a particular query on the data, as opposed to providing a dynamic view of a subset of the data, use the <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> methods of the **DataView** to achieve best performance rather than setting the **RowFilter** property.</span></span> <span data-ttu-id="bf7b4-110">L'impostazione di **RowFilter** proprietà ricompilato l'indice per i dati, aggiungendo un sovraccarico all'applicazione e riducendo le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="bf7b4-110">Setting the **RowFilter** property rebuilds the index for the data, adding overhead to your application and decreasing performance.</span></span> <span data-ttu-id="bf7b4-111">Il **RowFilter** proprietà è più adatta in un'applicazione con associazione a dati in cui i risultati filtrati vengono visualizzati da un controllo associato.</span><span class="sxs-lookup"><span data-stu-id="bf7b4-111">The **RowFilter** property is best used in a data-bound application where a bound control displays filtered results.</span></span> <span data-ttu-id="bf7b4-112">Il **trovare** e **FindRows** metodi si avvalgono dell'indice corrente senza richiedere l'indice da ricompilare.</span><span class="sxs-lookup"><span data-stu-id="bf7b4-112">The **Find** and **FindRows** methods leverage the current index without requiring the index to be rebuilt.</span></span> <span data-ttu-id="bf7b4-113">Per ulteriori informazioni sul **trovare** e **FindRows** metodi, vedere [ricerca righe](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md).</span><span class="sxs-lookup"><span data-stu-id="bf7b4-113">For more information about the **Find** and **FindRows** methods, see [Finding Rows](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md).</span></span>  
  
-   <span data-ttu-id="bf7b4-114">La proprietà <xref:System.Data.DataView.RowStateFilter%2A> consente di specificare le versioni di riga da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="bf7b4-114">You can use the <xref:System.Data.DataView.RowStateFilter%2A> property to specify which row versions to view.</span></span> <span data-ttu-id="bf7b4-115">Il **DataView** gestisce in modo implicito la versione di riga per esporre varia a seconda di **RowState** della riga sottostante.</span><span class="sxs-lookup"><span data-stu-id="bf7b4-115">The **DataView** implicitly manages which row version to expose depending upon the **RowState** of the underlying row.</span></span> <span data-ttu-id="bf7b4-116">Ad esempio, se il **RowStateFilter** è impostata su **DataViewRowState. Deleted**, **DataView** espone il **originale** versione di riga tutti **Deleted** righe in quanto non esiste alcun **corrente** versione di riga.</span><span class="sxs-lookup"><span data-stu-id="bf7b4-116">For example, if the **RowStateFilter** is set to **DataViewRowState.Deleted**, the **DataView** exposes the **Original** row version of all **Deleted** rows because there is no **Current** row version.</span></span> <span data-ttu-id="bf7b4-117">È possibile determinare la versione di riga di una riga è esposto tramite la **RowVersion** proprietà del **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="bf7b4-117">You can determine which row version of a row is being exposed by using the **RowVersion** property of the **DataRowView**.</span></span>  
  
     <span data-ttu-id="bf7b4-118">Nella tabella seguente illustra le opzioni per **DataViewRowState**.</span><span class="sxs-lookup"><span data-stu-id="bf7b4-118">The following table shows the options for **DataViewRowState**.</span></span>  
  
    |<span data-ttu-id="bf7b4-119">Opzioni di DataViewRowState</span><span class="sxs-lookup"><span data-stu-id="bf7b4-119">DataViewRowState options</span></span>|<span data-ttu-id="bf7b4-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bf7b4-120">Description</span></span>|  
    |------------------------------|-----------------|  
    |<span data-ttu-id="bf7b4-121">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="bf7b4-121">**CurrentRows**</span></span>|<span data-ttu-id="bf7b4-122">Il **corrente** versione della riga di tutti i **Unchanged**, **Added**, e **Modified** righe.</span><span class="sxs-lookup"><span data-stu-id="bf7b4-122">The **Current** row version of all **Unchanged**, **Added**, and **Modified** rows.</span></span> <span data-ttu-id="bf7b4-123">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="bf7b4-123">This is the default.</span></span>|  
    |<span data-ttu-id="bf7b4-124">**Aggiunta**</span><span class="sxs-lookup"><span data-stu-id="bf7b4-124">**Added**</span></span>|<span data-ttu-id="bf7b4-125">Il **corrente** versione di riga all **Added** righe.</span><span class="sxs-lookup"><span data-stu-id="bf7b4-125">The **Current** row version of all **Added** rows.</span></span>|  
    |<span data-ttu-id="bf7b4-126">**Eliminato**</span><span class="sxs-lookup"><span data-stu-id="bf7b4-126">**Deleted**</span></span>|<span data-ttu-id="bf7b4-127">Il **originale** versione di riga all **Deleted** righe.</span><span class="sxs-lookup"><span data-stu-id="bf7b4-127">The **Original** row version of all **Deleted** rows.</span></span>|  
    |<span data-ttu-id="bf7b4-128">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="bf7b4-128">**ModifiedCurrent**</span></span>|<span data-ttu-id="bf7b4-129">Il **corrente** versione di riga all **Modified** righe.</span><span class="sxs-lookup"><span data-stu-id="bf7b4-129">The **Current** row version of all **Modified** rows.</span></span>|  
    |<span data-ttu-id="bf7b4-130">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="bf7b4-130">**ModifiedOriginal**</span></span>|<span data-ttu-id="bf7b4-131">Il **originale** versione di riga all **Modified** righe.</span><span class="sxs-lookup"><span data-stu-id="bf7b4-131">The **Original** row version of all **Modified** rows.</span></span>|  
    |<span data-ttu-id="bf7b4-132">**None**</span><span class="sxs-lookup"><span data-stu-id="bf7b4-132">**None**</span></span>|<span data-ttu-id="bf7b4-133">Nessuna riga.</span><span class="sxs-lookup"><span data-stu-id="bf7b4-133">No rows.</span></span>|  
    |<span data-ttu-id="bf7b4-134">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="bf7b4-134">**OriginalRows**</span></span>|<span data-ttu-id="bf7b4-135">Il **originale** versione della riga di tutti i **Unchanged**, **Modified**, e **Deleted** righe.</span><span class="sxs-lookup"><span data-stu-id="bf7b4-135">The **Original** row version of all **Unchanged**, **Modified**, and **Deleted** rows.</span></span>|  
    |<span data-ttu-id="bf7b4-136">**Non modificato**</span><span class="sxs-lookup"><span data-stu-id="bf7b4-136">**Unchanged**</span></span>|<span data-ttu-id="bf7b4-137">Il **corrente** versione di riga all **Unchanged** righe.</span><span class="sxs-lookup"><span data-stu-id="bf7b4-137">The **Current** row version of all **Unchanged** rows.</span></span>|  
  
 <span data-ttu-id="bf7b4-138">Per ulteriori informazioni sulla riga stati e le versioni di riga, vedere [stati delle righe e le versioni di riga](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="bf7b4-138">For more information about row states and row versions, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="bf7b4-139">Nell'esempio di codice seguente viene creata una visualizzazione in cui vengono mostrati tutti i prodotti il cui numero di unità disponibili in magazzino è inferiore o uguale al livello di riordinamento. I prodotti vengono ordinati prima in base all'identificatore del fornitore, quindi in base al nome del prodotto.</span><span class="sxs-lookup"><span data-stu-id="bf7b4-139">The following code example creates a view that shows all the products where the number of units in stock is less than or equal to the reorder level, sorted first by supplier ID and then by product name.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bf7b4-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf7b4-140">See Also</span></span>  
 <xref:System.Data.DataViewRowState>  
 <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [<span data-ttu-id="bf7b4-141">DataView</span><span class="sxs-lookup"><span data-stu-id="bf7b4-141">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="bf7b4-142">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="bf7b4-142">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
