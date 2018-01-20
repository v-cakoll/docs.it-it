---
title: DataView
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 5b79461a6fc3314ca4178e0f9b1cff1c468cc3e6
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="dataviews"></a><span data-ttu-id="a52f9-102">DataView</span><span class="sxs-lookup"><span data-stu-id="a52f9-102">DataViews</span></span>
<span data-ttu-id="a52f9-103">Un oggetto <xref:System.Data.DataView> consente di creare diverse visualizzazioni dei dati archiviati in un oggetto <xref:System.Data.DataTable>. Questa funzionalità è usata spesso nelle applicazioni di associazione dati.</span><span class="sxs-lookup"><span data-stu-id="a52f9-103">A <xref:System.Data.DataView> enables you to create different views of the data stored in a <xref:System.Data.DataTable>, a capability that is often used in data-binding applications.</span></span> <span data-ttu-id="a52f9-104">Utilizzando un **DataView**, è possibile esporre i dati in una tabella con diversi tipi di ordinamento ed è possibile filtrare i dati dello stato o in base a un'espressione di filtro di riga.</span><span class="sxs-lookup"><span data-stu-id="a52f9-104">Using a **DataView**, you can expose the data in a table with different sort orders, and you can filter the data by row state or based on a filter expression.</span></span>  
  
 <span data-ttu-id="a52f9-105">Oggetto **DataView** offre una visualizzazione dinamica dei dati nell'oggetto sottostante **DataTable**: contenuto, l'ordinamento e l'appartenenza riflettono le modifiche che si verificano.</span><span class="sxs-lookup"><span data-stu-id="a52f9-105">A **DataView** provides a dynamic view of data in the underlying **DataTable**: the content, ordering, and membership reflect changes as they occur.</span></span> <span data-ttu-id="a52f9-106">Questo comportamento è diverso dal **selezionare** metodo il **DataTable**, che restituisce un <xref:System.Data.DataRow> matrice da una tabella in base a un particolare ordine di filtro e/o di ordinamento: thiscontent riflette le modifiche apportate il sottostante nella tabella, ma l'appartenenza e di ordinamento restano statici.</span><span class="sxs-lookup"><span data-stu-id="a52f9-106">This behavior differs from the **Select** method of the **DataTable**, which returns a <xref:System.Data.DataRow> array from a table based on a particular filter and/or sort order: thiscontent reflects changes to the underlying table, but its membership and ordering remain static.</span></span> <span data-ttu-id="a52f9-107">Le funzionalità dinamiche del **DataView** rendono ideale per applicazioni di associazione dati.</span><span class="sxs-lookup"><span data-stu-id="a52f9-107">The dynamic capabilities of the **DataView** make it ideal for data-binding applications.</span></span>  
  
 <span data-ttu-id="a52f9-108">Oggetto **DataView** offre una visualizzazione dinamica di un singolo set di dati, analogamente a una vista di database, a cui è possibile applicare diverse di ordinamento e criteri di filtro.</span><span class="sxs-lookup"><span data-stu-id="a52f9-108">A **DataView** provides you with a dynamic view of a single set of data, much like a database view, to which you can apply different sorting and filtering criteria.</span></span> <span data-ttu-id="a52f9-109">A differenza di una vista di database, tuttavia, un **DataView** non può essere considerato come una tabella e non fornisce una visualizzazione di tabelle unite in join.</span><span class="sxs-lookup"><span data-stu-id="a52f9-109">Unlike a database view, however, a **DataView** cannot be treated as a table and cannot provide a view of joined tables.</span></span> <span data-ttu-id="a52f9-110">Inoltre, non è possibile escludere colonne presenti nella tabella di origine, né aggiungere colonne, quali le colonne computazionali, che non sono presenti nella tabella di origine.</span><span class="sxs-lookup"><span data-stu-id="a52f9-110">You also cannot exclude columns that exist in the source table, nor can you append columns, such as computational columns, that do not exist in the source table.</span></span>  
  
 <span data-ttu-id="a52f9-111">È possibile utilizzare un <xref:System.Data.DataView.DataViewManager%2A> per gestire le impostazioni di visualizzazione per tutte le tabelle in un **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="a52f9-111">You can use a <xref:System.Data.DataView.DataViewManager%2A> to manage view settings for all the tables in a **DataSet**.</span></span> <span data-ttu-id="a52f9-112">Il **DataViewManager** offre un modo pratico per gestire le impostazioni di visualizzazione predefinito per ogni tabella.</span><span class="sxs-lookup"><span data-stu-id="a52f9-112">The **DataViewManager** provides you with a convenient way to manage default view settings for each table.</span></span> <span data-ttu-id="a52f9-113">Quando si associa un controllo a più di una tabella di un **DataSet**, associazione a un **DataViewManager** è la scelta ideale.</span><span class="sxs-lookup"><span data-stu-id="a52f9-113">When binding a control to more than one table of a **DataSet**, binding to a **DataViewManager** is the ideal choice.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a52f9-114">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="a52f9-114">In This Section</span></span>  
 [<span data-ttu-id="a52f9-115">Creazione di un oggetto DataView</span><span class="sxs-lookup"><span data-stu-id="a52f9-115">Creating a DataView</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataview.md)  
 <span data-ttu-id="a52f9-116">Viene descritto come creare un **DataView** per un **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="a52f9-116">Describes how to create a **DataView** for a **DataTable**.</span></span>  
  
 [<span data-ttu-id="a52f9-117">Ordinamento e applicazione di filtri ai dati</span><span class="sxs-lookup"><span data-stu-id="a52f9-117">Sorting and Filtering Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 <span data-ttu-id="a52f9-118">Viene descritto come impostare le proprietà di un **DataView** per restituire subset di righe di dati che soddisfano i criteri di filtro specifici o per restituire dati in un particolare tipo di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="a52f9-118">Describes how to set the properties of a **DataView** to return subsets of data rows meeting specific filter criteria, or to return data in a particular sort order.</span></span>  
  
 [<span data-ttu-id="a52f9-119">Oggetti DataRow e DataRowView</span><span class="sxs-lookup"><span data-stu-id="a52f9-119">DataRows and DataRowViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datarows-and-datarowviews.md)  
 <span data-ttu-id="a52f9-120">Viene descritto come accedere ai dati esposti dal **DataView**.</span><span class="sxs-lookup"><span data-stu-id="a52f9-120">Describes how to access the data exposed by the **DataView**.</span></span>  
  
 [<span data-ttu-id="a52f9-121">Ricerca di righe</span><span class="sxs-lookup"><span data-stu-id="a52f9-121">Finding Rows</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md)  
 <span data-ttu-id="a52f9-122">Viene descritto come trovare una determinata riga in un **DataView**.</span><span class="sxs-lookup"><span data-stu-id="a52f9-122">Describes how to find a particular row in a **DataView**.</span></span>  
  
 [<span data-ttu-id="a52f9-123">Oggetti ChildView e relazioni</span><span class="sxs-lookup"><span data-stu-id="a52f9-123">ChildViews and Relations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/childviews-and-relations.md)  
 <span data-ttu-id="a52f9-124">Viene descritto come creare visualizzazioni dei dati da una relazione padre-figlio tramite un **DataView**.</span><span class="sxs-lookup"><span data-stu-id="a52f9-124">Describes how to create views of data from a parent-child relationship using a **DataView**.</span></span>  
  
 [<span data-ttu-id="a52f9-125">Modifica di oggetti DataView</span><span class="sxs-lookup"><span data-stu-id="a52f9-125">Modifying DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/modifying-dataviews.md)  
 <span data-ttu-id="a52f9-126">Viene descritto come modificare i dati nell'oggetto sottostante **DataTable** tramite il **DataView**, inclusa l'abilitazione o disabilitazione degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="a52f9-126">Describes how to modify the data in the underlying **DataTable** via the **DataView**, including enabling or disabling updates.</span></span>  
  
 [<span data-ttu-id="a52f9-127">Gestione di eventi DataView</span><span class="sxs-lookup"><span data-stu-id="a52f9-127">Handling DataView Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataview-events.md)  
 <span data-ttu-id="a52f9-128">Viene descritto come utilizzare il **ListChanged** eventi per ricevere notifiche quando il contenuto o l'ordine di un **DataView** viene aggiornata.</span><span class="sxs-lookup"><span data-stu-id="a52f9-128">Describes how to use the **ListChanged** event to receive notification when the contents or order of a **DataView** is being updated.</span></span>  
  
 [<span data-ttu-id="a52f9-129">Gestione di oggetti DataView</span><span class="sxs-lookup"><span data-stu-id="a52f9-129">Managing DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/managing-dataviews.md)  
 <span data-ttu-id="a52f9-130">Viene descritto come utilizzare un **DataViewManager** per gestire **DataView** le impostazioni per ogni tabella in un **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="a52f9-130">Describes how to use a **DataViewManager** to manage **DataView** settings for each table in a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a52f9-131">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="a52f9-131">Related Sections</span></span>  
 [<span data-ttu-id="a52f9-132">Applicazioni Web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a52f9-132">ASP.NET Web Applications</span></span>](http://msdn.microsoft.com/library/a812d7b7-049e-4234-a4c2-6acf690301f6)  
 <span data-ttu-id="a52f9-133">Vengono fornite informazioni generali e procedure passo passo dettagliate per la creazione di applicazioni, Web Form e servizi Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a52f9-133">Provides overviews and detailed, step-by-step procedures for creating ASP.NET applications, Web Forms, and Web Services.</span></span>  
  
 [<span data-ttu-id="a52f9-134">Applicazioni Windows</span><span class="sxs-lookup"><span data-stu-id="a52f9-134">Windows Applications</span></span>](http://msdn.microsoft.com/library/a6bb2180-09b1-4738-b9fd-7fb05fc92f23)  
 <span data-ttu-id="a52f9-135">Vengono fornite informazioni dettagliate sull'utilizzo di Windows Form e di applicazioni console.</span><span class="sxs-lookup"><span data-stu-id="a52f9-135">Provides detailed information about working with Windows Forms and console applications.</span></span>  
  
 [<span data-ttu-id="a52f9-136">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="a52f9-136">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="a52f9-137">Viene descritto il **DataSet** oggetto e come è possibile usarlo per gestire i dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a52f9-137">Describes the **DataSet** object and how you can use it to manage application data.</span></span>  
  
 [<span data-ttu-id="a52f9-138">DataTable</span><span class="sxs-lookup"><span data-stu-id="a52f9-138">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 <span data-ttu-id="a52f9-139">Viene descritto il **DataTable** oggetto e come è possibile utilizzare per gestire i dati dell'applicazione da solo o come parte di un **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="a52f9-139">Describes the **DataTable** object and how you can use it to manage application data by itself or as part of a **DataSet**.</span></span>  
  
 [<span data-ttu-id="a52f9-140">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a52f9-140">ADO.NET</span></span>](../../../../../docs/framework/data/adonet/index.md)  
 <span data-ttu-id="a52f9-141">Vengono descritti l'architettura e i componenti di ADO.NET e come usare ADO.NET per l'accesso alle origini dati esistenti e per la gestione dei dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a52f9-141">Describes the ADO.NET architecture and components, and how to use ADO.NET to access existing data sources and manage application data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a52f9-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a52f9-142">See Also</span></span>  
 [<span data-ttu-id="a52f9-143">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="a52f9-143">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
