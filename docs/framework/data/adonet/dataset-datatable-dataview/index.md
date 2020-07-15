---
title: Oggetti DataSet, DataTable e DataView
description: Vengono illustrati diversi modi per utilizzare un set di dati ADO.NET, una rappresentazione di dati residente in memoria che fornisce un modello di programmazione relazionale coerente.
ms.date: 03/30/2017
ms.assetid: 6d4c4b69-8919-4224-8a65-6cca1c61b48f
ms.openlocfilehash: 53e12f701b9be1938d62f46bbeb6e63d95c03386
ms.sourcegitcommit: e7748001b1cee80ced691d8a76ca814c0b02dd9b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86374507"
---
# <a name="datasets-datatables-and-dataviews"></a><span data-ttu-id="aec1f-103">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="aec1f-103">DataSets, DataTables, and DataViews</span></span>

<span data-ttu-id="aec1f-104">L'oggetto <xref:System.Data.DataSet> di ADO.NET è una rappresentazione di dati residente in memoria, che fornisce un modello di programmazione relazionale coerente indipendentemente dall'origine dati in esso contenuta.</span><span class="sxs-lookup"><span data-stu-id="aec1f-104">The ADO.NET <xref:System.Data.DataSet> is a memory-resident representation of data that provides a consistent relational programming model regardless of the source of the data it contains.</span></span> <span data-ttu-id="aec1f-105">Un <xref:System.Data.DataSet> rappresenta un set completo di dati che include le tabelle in cui sono contenuti, ordinati e vincolati i dati e le relazioni tra le tabelle.</span><span class="sxs-lookup"><span data-stu-id="aec1f-105">A <xref:System.Data.DataSet> represents a complete set of data including the tables that contain, order, and constrain the data, as well as the relationships between the tables.</span></span>  
  
<span data-ttu-id="aec1f-106">Per usare un <xref:System.Data.DataSet> sono disponibili numerosi metodi, che è possibile applicare singolarmente o in combinazione.</span><span class="sxs-lookup"><span data-stu-id="aec1f-106">There are several ways of working with a <xref:System.Data.DataSet>, which can be applied independently or in combination.</span></span> <span data-ttu-id="aec1f-107">È possibile:</span><span class="sxs-lookup"><span data-stu-id="aec1f-107">You can:</span></span>  
  
- <span data-ttu-id="aec1f-108">Creare a livello di programmazione degli oggetti <xref:System.Data.DataTable>, <xref:System.Data.DataRelation> e <xref:System.Data.Constraint> all'interno di un <xref:System.Data.DataSet> e compilare le tabelle con i dati.</span><span class="sxs-lookup"><span data-stu-id="aec1f-108">Programmatically create a <xref:System.Data.DataTable>, <xref:System.Data.DataRelation>, and <xref:System.Data.Constraint> within a <xref:System.Data.DataSet> and populate the tables with data.</span></span>  
  
- <span data-ttu-id="aec1f-109">Compilare il tipo <xref:System.Data.DataSet> con tabelle di dati provenienti da un'origine dati relazionale esistente usando un `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="aec1f-109">Populate the <xref:System.Data.DataSet> with tables of data from an existing relational data source using a `DataAdapter`.</span></span>  
  
- <span data-ttu-id="aec1f-110">Caricare e mantenere il contenuto del <xref:System.Data.DataSet> usando XML.</span><span class="sxs-lookup"><span data-stu-id="aec1f-110">Load and persist the <xref:System.Data.DataSet> contents using XML.</span></span> <span data-ttu-id="aec1f-111">Per altre informazioni, vedere [Uso di XML in un set di dati](using-xml-in-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="aec1f-111">For more information, see [Using XML in a DataSet](using-xml-in-a-dataset.md).</span></span>  
  
<span data-ttu-id="aec1f-112">Un <xref:System.Data.DataSet> tipizzato in modo sicuro può anche essere trasportato usando un servizio Web XML.</span><span class="sxs-lookup"><span data-stu-id="aec1f-112">A strongly typed <xref:System.Data.DataSet> can also be transported using an XML Web service.</span></span> <span data-ttu-id="aec1f-113">Grazie alla struttura che lo caratterizza, il <xref:System.Data.DataSet> è ideale per il trasporto di dati tramite i servizi Web XML.</span><span class="sxs-lookup"><span data-stu-id="aec1f-113">The design of the <xref:System.Data.DataSet> makes it ideal for transporting data using XML Web services.</span></span> <span data-ttu-id="aec1f-114">Per una panoramica dei servizi Web XML, vedere [Panoramica dei servizi Web XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w9fdtx28(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="aec1f-114">For an overview of XML Web services, see [XML Web Services Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w9fdtx28(v=vs.100)).</span></span> <span data-ttu-id="aec1f-115">Per un esempio di utilizzo di un <xref:System.Data.DataSet> da un servizio Web XML, vedere [Uso di un set di dati da un servizio Web XML](consuming-a-dataset-from-an-xml-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="aec1f-115">For an example of consuming a <xref:System.Data.DataSet> from an XML Web service, see [Consuming a DataSet from an XML Web Service](consuming-a-dataset-from-an-xml-web-service.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aec1f-116">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="aec1f-116">In this section</span></span>

 [<span data-ttu-id="aec1f-117">Indicazioni sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="aec1f-117">Security guidance</span></span>](security-guidance.md)  
 <span data-ttu-id="aec1f-118">Fornisce indicazioni sulla sicurezza per <xref:System.Data.DataSet> e <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="aec1f-118">Provides security guidance for <xref:System.Data.DataSet> and <xref:System.Data.DataTable>.</span></span>

 [<span data-ttu-id="aec1f-119">Creazione di un set di dati</span><span class="sxs-lookup"><span data-stu-id="aec1f-119">Creating a DataSet</span></span>](creating-a-dataset.md)  
 <span data-ttu-id="aec1f-120">Viene descritta la sintassi per la creazione di un'istanza di un tipo <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="aec1f-120">Describes the syntax for creating an instance of a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="aec1f-121">Aggiunta di un oggetto DataTable a un dataset</span><span class="sxs-lookup"><span data-stu-id="aec1f-121">Adding a DataTable to a DataSet</span></span>](adding-a-datatable-to-a-dataset.md)  
 <span data-ttu-id="aec1f-122">Viene descritto come creare e aggiungere tabelle e colonne a un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="aec1f-122">Describes how to create and add tables and columns to a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="aec1f-123">Aggiunta di oggetti DataRelation</span><span class="sxs-lookup"><span data-stu-id="aec1f-123">Adding DataRelations</span></span>](adding-datarelations.md)  
 <span data-ttu-id="aec1f-124">Viene descritto come creare le relazioni tra tabelle in un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="aec1f-124">Describes how to create relations between tables in a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="aec1f-125">Esplorazione di oggetti DataRelation</span><span class="sxs-lookup"><span data-stu-id="aec1f-125">Navigating DataRelations</span></span>](navigating-datarelations.md)  
 <span data-ttu-id="aec1f-126">Viene descritto come usare le relazioni tra tabelle in un <xref:System.Data.DataSet> per restituire le righe padre o figlio di una relazione padre-figlio.</span><span class="sxs-lookup"><span data-stu-id="aec1f-126">Describes how to use the relations between tables in a <xref:System.Data.DataSet> to return the child or parent rows of a parent-child relationship.</span></span>  
  
 [<span data-ttu-id="aec1f-127">Unione di contenuti di set di dati</span><span class="sxs-lookup"><span data-stu-id="aec1f-127">Merging DataSet Contents</span></span>](merging-dataset-contents.md)  
 <span data-ttu-id="aec1f-128">Viene descritto come unire il contenuto di una matrice di <xref:System.Data.DataSet>, <xref:System.Data.DataTable> o <xref:System.Data.DataRow> in un altro <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="aec1f-128">Describes how to merge the contents of one <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, or <xref:System.Data.DataRow> array into another <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="aec1f-129">Copia di contenuti di dataset</span><span class="sxs-lookup"><span data-stu-id="aec1f-129">Copying DataSet Contents</span></span>](copying-dataset-contents.md)  
 <span data-ttu-id="aec1f-130">Viene descritto come creare una copia di un <xref:System.Data.DataSet> in cui possa essere contenuto lo schema e i dati specificati.</span><span class="sxs-lookup"><span data-stu-id="aec1f-130">Describes how to create a copy of a <xref:System.Data.DataSet> that can contain schema as well as specified data.</span></span>  
  
 [<span data-ttu-id="aec1f-131">Gestione di eventi dataset</span><span class="sxs-lookup"><span data-stu-id="aec1f-131">Handling DataSet Events</span></span>](handling-dataset-events.md)  
 <span data-ttu-id="aec1f-132">Vengono descritti gli eventi di un <xref:System.Data.DataSet> e il relativo uso.</span><span class="sxs-lookup"><span data-stu-id="aec1f-132">Describes the events of a <xref:System.Data.DataSet> and how to use them.</span></span>  
  
 [<span data-ttu-id="aec1f-133">Dataset tipizzati</span><span class="sxs-lookup"><span data-stu-id="aec1f-133">Typed DataSets</span></span>](typed-datasets.md)  
 <span data-ttu-id="aec1f-134">Vengono illustrate le caratteristiche di un <xref:System.Data.DataSet> tipizzato e viene descritto come crearlo e usarlo.</span><span class="sxs-lookup"><span data-stu-id="aec1f-134">Discusses what a typed <xref:System.Data.DataSet> is and how to create and use it.</span></span>  
  
 [<span data-ttu-id="aec1f-135">DataTable</span><span class="sxs-lookup"><span data-stu-id="aec1f-135">DataTables</span></span>](datatables.md)  
 <span data-ttu-id="aec1f-136">Viene descritto come creare una <xref:System.Data.DataTable>, definire lo schema e modificare i dati.</span><span class="sxs-lookup"><span data-stu-id="aec1f-136">Describes how to create a <xref:System.Data.DataTable>, define the schema, and manipulate data.</span></span>  
  
 [<span data-ttu-id="aec1f-137">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="aec1f-137">DataTableReaders</span></span>](datatablereaders.md)  
 <span data-ttu-id="aec1f-138">Viene descritto come creare e usare un oggetto <xref:System.Data.DataTableReader>.</span><span class="sxs-lookup"><span data-stu-id="aec1f-138">Describes how to create and use a <xref:System.Data.DataTableReader>.</span></span>  
  
 [<span data-ttu-id="aec1f-139">DataView</span><span class="sxs-lookup"><span data-stu-id="aec1f-139">DataViews</span></span>](dataviews.md)  
 <span data-ttu-id="aec1f-140">Viene descritto come creare e usare `DataViews` e come usare eventi <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="aec1f-140">Describes how to create and work with `DataViews` and work with <xref:System.Data.DataView> events.</span></span>  
  
 [<span data-ttu-id="aec1f-141">Utilizzo di XML in un dataset</span><span class="sxs-lookup"><span data-stu-id="aec1f-141">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="aec1f-142">Viene descritta l'interazione del <xref:System.Data.DataSet> con XML come origine dati, inclusi il caricamento e il mantenimento del contenuto di un <xref:System.Data.DataSet> sotto forma di dati XML.</span><span class="sxs-lookup"><span data-stu-id="aec1f-142">Describes how the <xref:System.Data.DataSet> interacts with XML as a data source, including loading and persisting the contents of a <xref:System.Data.DataSet> as XML data.</span></span>  
  
 [<span data-ttu-id="aec1f-143">Utilizzo di un dataset da un servizio Web XML</span><span class="sxs-lookup"><span data-stu-id="aec1f-143">Consuming a DataSet from an XML Web Service</span></span>](consuming-a-dataset-from-an-xml-web-service.md)  
 <span data-ttu-id="aec1f-144">Viene descritto come creare un servizio Web XML che usa un <xref:System.Data.DataSet> per trasportare i dati.</span><span class="sxs-lookup"><span data-stu-id="aec1f-144">Describes how to create an XML Web service that uses a <xref:System.Data.DataSet> to transport data.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="aec1f-145">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="aec1f-145">Related sections</span></span>

 [<span data-ttu-id="aec1f-146">Novità in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="aec1f-146">What's New in ADO.NET</span></span>](../whats-new.md)  
 <span data-ttu-id="aec1f-147">Vengono descritte le nuove funzionalità di ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="aec1f-147">Introduces features that are new in ADO.NET.</span></span>  
  
 [<span data-ttu-id="aec1f-148">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="aec1f-148">ADO.NET Overview</span></span>](../ado-net-overview.md)  
 <span data-ttu-id="aec1f-149">Viene fornita un'introduzione alle caratteristiche e ai componenti di ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="aec1f-149">Provides an introduction to the design and components of ADO.NET.</span></span>  
  
 [<span data-ttu-id="aec1f-150">Popolamento di un set di dati da un oggetto DataAdapter</span><span class="sxs-lookup"><span data-stu-id="aec1f-150">Populating a DataSet from a DataAdapter</span></span>](../populating-a-dataset-from-a-dataadapter.md)  
 <span data-ttu-id="aec1f-151">Viene descritto come caricare un **DataSet** con dati da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="aec1f-151">Describes how to load a **DataSet** with data from a data source.</span></span>  
  
 [<span data-ttu-id="aec1f-152">Aggiornamento di origini dati con DataAdapter</span><span class="sxs-lookup"><span data-stu-id="aec1f-152">Updating Data Sources with DataAdapters</span></span>](../updating-data-sources-with-dataadapters.md)  
 <span data-ttu-id="aec1f-153">Viene descritto come applicare le modifiche apportate ai dati di un **DataSet** nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="aec1f-153">Describes how to resolve changes to the data in a **DataSet** back to the data source.</span></span>  
  
 [<span data-ttu-id="aec1f-154">Aggiunta di vincoli esistenti a un dataset</span><span class="sxs-lookup"><span data-stu-id="aec1f-154">Adding Existing Constraints to a DataSet</span></span>](../adding-existing-constraints-to-a-dataset.md)  
 <span data-ttu-id="aec1f-155">Viene descritto come compilare un **DataSet** con informazioni relative alla chiave primaria provenienti da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="aec1f-155">Describes how to populate a **DataSet** with primary key information from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aec1f-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aec1f-156">See also</span></span>

- [<span data-ttu-id="aec1f-157">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="aec1f-157">ADO.NET</span></span>](../index.md)
- [<span data-ttu-id="aec1f-158">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="aec1f-158">ADO.NET Overview</span></span>](../ado-net-overview.md)
