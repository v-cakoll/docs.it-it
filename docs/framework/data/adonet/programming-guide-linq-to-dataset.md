---
title: Guida per programmatori (LINQ to DataSet)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 977aedd7-0084-46a0-b56f-345787a55da1
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 298ff0c6bfc5bc251483de8e90e3a394a2337369
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="programming-guide-linq-to-dataset"></a><span data-ttu-id="9bc97-102">Guida per programmatori (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="9bc97-102">Programming Guide (LINQ to DataSet)</span></span>
<span data-ttu-id="9bc97-103">Contenuto della sezione vengono fornite informazioni di carattere concettuale ed esempi per programmare con [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9bc97-103">This section provides conceptual information and examples for programming with [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9bc97-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="9bc97-104">In This Section</span></span>  
 [<span data-ttu-id="9bc97-105">Query in LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="9bc97-105">Queries in LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/queries-in-linq-to-dataset.md)  
 <span data-ttu-id="9bc97-106">Vengono fornite informazioni sulla scrittura di query [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9bc97-106">Provides information about how to write [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] queries.</span></span>  
  
 [<span data-ttu-id="9bc97-107">Esecuzione di query su oggetti DataSet</span><span class="sxs-lookup"><span data-stu-id="9bc97-107">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 <span data-ttu-id="9bc97-108">Viene descritto come eseguire una query su oggetti <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="9bc97-108">Describes how to query <xref:System.Data.DataSet> objects.</span></span>  
  
 [<span data-ttu-id="9bc97-109">Confronto di DataRows</span><span class="sxs-lookup"><span data-stu-id="9bc97-109">Comparing DataRows</span></span>](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md)  
 <span data-ttu-id="9bc97-110">Viene descritto come usare l'oggetto <xref:System.Data.DataRowComparer> per confrontare righe di dati.</span><span class="sxs-lookup"><span data-stu-id="9bc97-110">Describes how to use the <xref:System.Data.DataRowComparer> object to compare data rows.</span></span>  
  
 [<span data-ttu-id="9bc97-111">Creazione di un oggetto DataTable da una query</span><span class="sxs-lookup"><span data-stu-id="9bc97-111">Creating a DataTable From a Query</span></span>](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md)  
 <span data-ttu-id="9bc97-112">Vengono fornite informazioni sulla creazione di un <xref:System.Data.DataTable> da un [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query utilizzando il <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="9bc97-112">Provides information about creating a <xref:System.Data.DataTable> from a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [<span data-ttu-id="9bc97-113">Procedura: implementare CopyToDataTable\<T > in cui il tipo generico T non è un DataRow</span><span class="sxs-lookup"><span data-stu-id="9bc97-113">How to: Implement CopyToDataTable\<T> Where the Generic Type T Is Not a DataRow</span></span>](../../../../docs/framework/data/adonet/implement-copytodatatable-where-type-not-a-datarow.md)  
 <span data-ttu-id="9bc97-114">Viene descritto come implementare un metodo `CopyToDataTable<T>` personalizzato in cui il parametro generico T non è di tipo <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="9bc97-114">Describes how to implement a custom `CopyToDataTable<T>` method where the generic parameter T is not of type <xref:System.Data.DataRow>.</span></span>  
  
 [<span data-ttu-id="9bc97-115">Metodi generici Field e SetField</span><span class="sxs-lookup"><span data-stu-id="9bc97-115">Generic Field and SetField Methods</span></span>](../../../../docs/framework/data/adonet/generic-field-and-setfield-methods-linq-to-dataset.md)  
 <span data-ttu-id="9bc97-116">Vengono fornite informazioni sui metodi <xref:System.Data.DataRowExtensions.Field%2A> e <xref:System.Data.DataRowExtensions.SetField%2A> generici.</span><span class="sxs-lookup"><span data-stu-id="9bc97-116">Provides information about the generic <xref:System.Data.DataRowExtensions.Field%2A> and <xref:System.Data.DataRowExtensions.SetField%2A> methods.</span></span>  
  
 [<span data-ttu-id="9bc97-117">Data binding e LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="9bc97-117">Data Binding and LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)  
 <span data-ttu-id="9bc97-118">Viene descritto il processo di associazione dati usando l'oggetto <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="9bc97-118">Describes databinding using the <xref:System.Data.DataView> object.</span></span>  
  
 [<span data-ttu-id="9bc97-119">Debug di query di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="9bc97-119">Debugging LINQ to DataSet Queries</span></span>](../../../../docs/framework/data/adonet/debugging-linq-to-dataset-queries.md)  
 <span data-ttu-id="9bc97-120">Fornisce informazioni sul debug e risoluzione dei problemi [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query.</span><span class="sxs-lookup"><span data-stu-id="9bc97-120">Provides information about debugging and troubleshooting [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] queries.</span></span>  
  
 [<span data-ttu-id="9bc97-121">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="9bc97-121">Security</span></span>](../../../../docs/framework/data/adonet/security-linq-to-dataset.md)  
 <span data-ttu-id="9bc97-122">Vengono illustrati i problemi di sicurezza in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9bc97-122">Describes security issues in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span>  
  
 [<span data-ttu-id="9bc97-123">Esempi di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="9bc97-123">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 <span data-ttu-id="9bc97-124">Vengono forniti esempi di query in cui vengono usati operatori [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9bc97-124">Provides query examples that use the [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] operators.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9bc97-125">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="9bc97-125">Reference</span></span>  
 <xref:System.Data.DataRowComparer>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataView>  
  
## <a name="see-also"></a><span data-ttu-id="9bc97-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9bc97-126">See Also</span></span>  
 [<span data-ttu-id="9bc97-127">LINQ to ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9bc97-127">LINQ to ADO.NET</span></span>](http://msdn.microsoft.com/en-us/be3297b9-1b54-4d4c-82a8-add0d79c2006)  
 [<span data-ttu-id="9bc97-128">NOT IN BUILD: Guida di programmazione generale LINQ</span><span class="sxs-lookup"><span data-stu-id="9bc97-128">NOT IN BUILD: LINQ General Programming Guide</span></span>](http://msdn.microsoft.com/en-us/609c7a6b-cbdd-429d-99f3-78d13d3bc049)  
 [<span data-ttu-id="9bc97-129">Framework LINQ</span><span class="sxs-lookup"><span data-stu-id="9bc97-129">LINQ Framework</span></span>](http://msdn.microsoft.com/en-us/897ea0fc-40db-4694-bbe5-7dd339d5bf94)
