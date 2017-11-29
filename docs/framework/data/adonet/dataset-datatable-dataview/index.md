---
title: Oggetti DataSet, DataTable e DataView
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d4c4b69-8919-4224-8a65-6cca1c61b48f
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 642a81b926262fb8ea95234d90e4c1a0c49ea96c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="datasets-datatables-and-dataviews"></a><span data-ttu-id="14bab-102">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="14bab-102">DataSets, DataTables, and DataViews</span></span>
<span data-ttu-id="14bab-103">L'oggetto <xref:System.Data.DataSet> di ADO.NET è una rappresentazione di dati residente in memoria, che fornisce un modello di programmazione relazionale coerente indipendentemente dall'origine dati in esso contenuta.</span><span class="sxs-lookup"><span data-stu-id="14bab-103">The ADO.NET <xref:System.Data.DataSet> is a memory-resident representation of data that provides a consistent relational programming model regardless of the source of the data it contains.</span></span> <span data-ttu-id="14bab-104">Un <xref:System.Data.DataSet> rappresenta un set completo di dati che include le tabelle in cui sono contenuti, ordinati e vincolati i dati e le relazioni tra le tabelle.</span><span class="sxs-lookup"><span data-stu-id="14bab-104">A <xref:System.Data.DataSet> represents a complete set of data including the tables that contain, order, and constrain the data, as well as the relationships between the tables.</span></span>  
  
 <span data-ttu-id="14bab-105">Per usare un <xref:System.Data.DataSet> sono disponibili numerosi metodi, che è possibile applicare singolarmente o in combinazione.</span><span class="sxs-lookup"><span data-stu-id="14bab-105">There are several ways of working with a <xref:System.Data.DataSet>, which can be applied independently or in combination.</span></span> <span data-ttu-id="14bab-106">È possibile:</span><span class="sxs-lookup"><span data-stu-id="14bab-106">You can:</span></span>  
  
-   <span data-ttu-id="14bab-107">Creare a livello di programmazione degli oggetti <xref:System.Data.DataTable>, <xref:System.Data.DataRelation> e <xref:System.Data.Constraint> all'interno di un <xref:System.Data.DataSet> e compilare le tabelle con i dati.</span><span class="sxs-lookup"><span data-stu-id="14bab-107">Programmatically create a <xref:System.Data.DataTable>, <xref:System.Data.DataRelation>, and <xref:System.Data.Constraint> within a <xref:System.Data.DataSet> and populate the tables with data.</span></span>  
  
-   <span data-ttu-id="14bab-108">Compilare il tipo <xref:System.Data.DataSet> con tabelle di dati provenienti da un'origine dati relazionale esistente usando un `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="14bab-108">Populate the <xref:System.Data.DataSet> with tables of data from an existing relational data source using a `DataAdapter`.</span></span>  
  
-   <span data-ttu-id="14bab-109">Caricare e mantenere il contenuto del <xref:System.Data.DataSet> usando XML.</span><span class="sxs-lookup"><span data-stu-id="14bab-109">Load and persist the <xref:System.Data.DataSet> contents using XML.</span></span> <span data-ttu-id="14bab-110">Per altre informazioni, vedere [Uso di XML in un set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="14bab-110">For more information, see [Using XML in a DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).</span></span>  
  
 <span data-ttu-id="14bab-111">Un <xref:System.Data.DataSet> tipizzato in modo sicuro può anche essere trasportato usando un servizio Web XML.</span><span class="sxs-lookup"><span data-stu-id="14bab-111">A strongly typed <xref:System.Data.DataSet> can also be transported using an XML Web service.</span></span> <span data-ttu-id="14bab-112">Grazie alla struttura che lo caratterizza, il <xref:System.Data.DataSet> è ideale per il trasporto di dati tramite i servizi Web XML.</span><span class="sxs-lookup"><span data-stu-id="14bab-112">The design of the <xref:System.Data.DataSet> makes it ideal for transporting data using XML Web services.</span></span> <span data-ttu-id="14bab-113">Per una panoramica dei servizi Web XML, vedere [Panoramica dei servizi Web XML](http://msdn.microsoft.com/en-us/9db0c7b8-bca6-462b-9be5-f5f9a7f05a4d).</span><span class="sxs-lookup"><span data-stu-id="14bab-113">For an overview of XML Web services, see [XML Web Services Overview](http://msdn.microsoft.com/en-us/9db0c7b8-bca6-462b-9be5-f5f9a7f05a4d).</span></span> <span data-ttu-id="14bab-114">Per un esempio di utilizzo di un <xref:System.Data.DataSet> da un servizio Web XML, vedere [Uso di un set di dati da un servizio Web XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="14bab-114">For an example of consuming a <xref:System.Data.DataSet> from an XML Web service, see [Consuming a DataSet from an XML Web Service](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="14bab-115">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="14bab-115">In This Section</span></span>  
 [<span data-ttu-id="14bab-116">Creazione di un set di dati</span><span class="sxs-lookup"><span data-stu-id="14bab-116">Creating a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataset.md)  
 <span data-ttu-id="14bab-117">Viene descritta la sintassi per la creazione di un'istanza di un tipo <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="14bab-117">Describes the syntax for creating an instance of a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="14bab-118">Aggiunta di un oggetto DataTable a un set di dati</span><span class="sxs-lookup"><span data-stu-id="14bab-118">Adding a DataTable to a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-a-datatable-to-a-dataset.md)  
 <span data-ttu-id="14bab-119">Viene descritto come creare e aggiungere tabelle e colonne a un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="14bab-119">Describes how to create and add tables and columns to a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="14bab-120">Aggiunta di oggetti DataRelation</span><span class="sxs-lookup"><span data-stu-id="14bab-120">Adding DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)  
 <span data-ttu-id="14bab-121">Viene descritto come creare le relazioni tra tabelle in un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="14bab-121">Describes how to create relations between tables in a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="14bab-122">Esplorazione di oggetti DataRelation</span><span class="sxs-lookup"><span data-stu-id="14bab-122">Navigating DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datarelations.md)  
 <span data-ttu-id="14bab-123">Viene descritto come usare le relazioni tra tabelle in un <xref:System.Data.DataSet> per restituire le righe padre o figlio di una relazione padre-figlio.</span><span class="sxs-lookup"><span data-stu-id="14bab-123">Describes how to use the relations between tables in a <xref:System.Data.DataSet> to return the child or parent rows of a parent-child relationship.</span></span>  
  
 [<span data-ttu-id="14bab-124">Unione di contenuti di set di dati</span><span class="sxs-lookup"><span data-stu-id="14bab-124">Merging DataSet Contents</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/merging-dataset-contents.md)  
 <span data-ttu-id="14bab-125">Viene descritto come unire il contenuto di una matrice di <xref:System.Data.DataSet>, <xref:System.Data.DataTable> o <xref:System.Data.DataRow> in un altro <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="14bab-125">Describes how to merge the contents of one <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, or <xref:System.Data.DataRow> array into another <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="14bab-126">Copia di contenuti di set di dati</span><span class="sxs-lookup"><span data-stu-id="14bab-126">Copying DataSet Contents</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/copying-dataset-contents.md)  
 <span data-ttu-id="14bab-127">Viene descritto come creare una copia di un <xref:System.Data.DataSet> in cui possa essere contenuto lo schema e i dati specificati.</span><span class="sxs-lookup"><span data-stu-id="14bab-127">Describes how to create a copy of a <xref:System.Data.DataSet> that can contain schema as well as specified data.</span></span>  
  
 [<span data-ttu-id="14bab-128">Gestione di eventi di set di dati</span><span class="sxs-lookup"><span data-stu-id="14bab-128">Handling DataSet Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataset-events.md)  
 <span data-ttu-id="14bab-129">Vengono descritti gli eventi di un <xref:System.Data.DataSet> e il relativo uso.</span><span class="sxs-lookup"><span data-stu-id="14bab-129">Describes the events of a <xref:System.Data.DataSet> and how to use them.</span></span>  
  
 [<span data-ttu-id="14bab-130">Set di dati tipizzati</span><span class="sxs-lookup"><span data-stu-id="14bab-130">Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 <span data-ttu-id="14bab-131">Vengono illustrate le caratteristiche di un <xref:System.Data.DataSet> tipizzato e viene descritto come crearlo e usarlo.</span><span class="sxs-lookup"><span data-stu-id="14bab-131">Discusses what a typed <xref:System.Data.DataSet> is and how to create and use it.</span></span>  
  
 [<span data-ttu-id="14bab-132">DataTable</span><span class="sxs-lookup"><span data-stu-id="14bab-132">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 <span data-ttu-id="14bab-133">Viene descritto come creare una <xref:System.Data.DataTable>, definire lo schema e modificare i dati.</span><span class="sxs-lookup"><span data-stu-id="14bab-133">Describes how to create a <xref:System.Data.DataTable>, define the schema, and manipulate data.</span></span>  
  
 [<span data-ttu-id="14bab-134">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="14bab-134">DataTableReaders</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)  
 <span data-ttu-id="14bab-135">Viene descritto come creare e usare un oggetto <xref:System.Data.DataTableReader>.</span><span class="sxs-lookup"><span data-stu-id="14bab-135">Describes how to create and use a <xref:System.Data.DataTableReader>.</span></span>  
  
 [<span data-ttu-id="14bab-136">DataView</span><span class="sxs-lookup"><span data-stu-id="14bab-136">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 <span data-ttu-id="14bab-137">Viene descritto come creare e usare `DataViews` e come usare eventi <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="14bab-137">Describes how to create and work with `DataViews` and work with <xref:System.Data.DataView> events.</span></span>  
  
 [<span data-ttu-id="14bab-138">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="14bab-138">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 <span data-ttu-id="14bab-139">Viene descritta l'interazione del <xref:System.Data.DataSet> con XML come origine dati, inclusi il caricamento e il mantenimento del contenuto di un <xref:System.Data.DataSet> sotto forma di dati XML.</span><span class="sxs-lookup"><span data-stu-id="14bab-139">Describes how the <xref:System.Data.DataSet> interacts with XML as a data source, including loading and persisting the contents of a <xref:System.Data.DataSet> as XML data.</span></span>  
  
 [<span data-ttu-id="14bab-140">Utilizzo di un set di dati da un servizio Web XML</span><span class="sxs-lookup"><span data-stu-id="14bab-140">Consuming a DataSet from an XML Web Service</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md)  
 <span data-ttu-id="14bab-141">Viene descritto come creare un servizio Web XML che usa un <xref:System.Data.DataSet> per trasportare i dati.</span><span class="sxs-lookup"><span data-stu-id="14bab-141">Describes how to create an XML Web service that uses a <xref:System.Data.DataSet> to transport data.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="14bab-142">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="14bab-142">Related Sections</span></span>  
 [<span data-ttu-id="14bab-143">Novità in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="14bab-143">What's New in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/whats-new.md)  
 <span data-ttu-id="14bab-144">Vengono descritte le nuove funzionalità di ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="14bab-144">Introduces features that are new in ADO.NET.</span></span>  
  
 [<span data-ttu-id="14bab-145">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="14bab-145">ADO.NET Overview</span></span>](../../../../../docs/framework/data/adonet/ado-net-overview.md)  
 <span data-ttu-id="14bab-146">Viene fornita un'introduzione alle caratteristiche e ai componenti di ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="14bab-146">Provides an introduction to the design and components of ADO.NET.</span></span>  
  
 [<span data-ttu-id="14bab-147">Popolamento di un set di dati da un oggetto DataAdapter</span><span class="sxs-lookup"><span data-stu-id="14bab-147">Populating a DataSet from a DataAdapter</span></span>](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 <span data-ttu-id="14bab-148">Viene descritto come caricare un **DataSet** con dati da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="14bab-148">Describes how to load a **DataSet** with data from a data source.</span></span>  
  
 [<span data-ttu-id="14bab-149">Aggiornamento di origini dati con DataAdapter</span><span class="sxs-lookup"><span data-stu-id="14bab-149">Updating Data Sources with DataAdapters</span></span>](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 <span data-ttu-id="14bab-150">Viene descritto come applicare le modifiche apportate ai dati di un **DataSet** nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="14bab-150">Describes how to resolve changes to the data in a **DataSet** back to the data source.</span></span>  
  
 [<span data-ttu-id="14bab-151">Aggiunta di vincoli esistenti a un set di dati</span><span class="sxs-lookup"><span data-stu-id="14bab-151">Adding Existing Constraints to a DataSet</span></span>](../../../../../docs/framework/data/adonet/adding-existing-constraints-to-a-dataset.md)  
 <span data-ttu-id="14bab-152">Viene descritto come compilare un **DataSet** con informazioni relative alla chiave primaria provenienti da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="14bab-152">Describes how to populate a **DataSet** with primary key information from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14bab-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14bab-153">See Also</span></span>  
 [<span data-ttu-id="14bab-154">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="14bab-154">ADO.NET</span></span>](../../../../../docs/framework/data/adonet/index.md)  
 [<span data-ttu-id="14bab-155">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="14bab-155">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
