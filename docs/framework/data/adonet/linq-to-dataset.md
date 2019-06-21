---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: 36335f90c7850fa00a15e7112b7473637250c656
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/21/2019
ms.locfileid: "67306241"
---
# <a name="linq-to-dataset"></a><span data-ttu-id="5301c-102">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="5301c-102">LINQ to DataSet</span></span>
<span data-ttu-id="5301c-103">Con [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] è più facile e veloce eseguire una query su dati memorizzati nella cache di un oggetto <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="5301c-103">[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] makes it easier and faster to query over data cached in a <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="5301c-104">In particolare, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] semplifica l'esecuzione di query, consentendo agli sviluppatori di scrivere query dal linguaggio di programmazione stesso, anziché tramite un linguaggio di query separata.</span><span class="sxs-lookup"><span data-stu-id="5301c-104">Specifically, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] simplifies querying by enabling developers to write queries from the programming language itself, instead of by using a separate query language.</span></span> <span data-ttu-id="5301c-105">Ciò è particolarmente utile per gli sviluppatori di Visual Studio, che possono ora sfruttare i vantaggi del controllo della sintassi in fase di compilazione, tipizzazione statica e supporto IntelliSense resi disponibili da Visual Studio nelle query.</span><span class="sxs-lookup"><span data-stu-id="5301c-105">This is especially useful for Visual Studio developers, who can now take advantage of the compile-time syntax checking, static typing, and IntelliSense support provided by the Visual Studio in their queries.</span></span>  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] <span data-ttu-id="5301c-106">può inoltre essere usato per eseguire query su dati che sono stati consolidati da una o più origini dati.</span><span class="sxs-lookup"><span data-stu-id="5301c-106">can also be used to query over data that has been consolidated from one or more data sources.</span></span> <span data-ttu-id="5301c-107">In tal modo sono possibili molti scenari in cui è necessario rappresentare e gestire i dati con flessibilità, ad esempio per le query su dati aggregati localmente e la memorizzazione nella cache di livello intermedio nelle applicazioni Web.</span><span class="sxs-lookup"><span data-stu-id="5301c-107">This enables many scenarios that require flexibility in how data is represented and handled, such as querying locally aggregated data and middle-tier caching in Web applications.</span></span> <span data-ttu-id="5301c-108">In particolare, questo tipo di modifiche sono richieste nelle applicazioni generiche per la creazione di rapporti, di analisi e di Business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="5301c-108">In particular, generic reporting, analysis, and business intelligence applications require this method of manipulation.</span></span>  
  
 <span data-ttu-id="5301c-109">Il [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] la funzionalità è esposta principalmente tramite i metodi di estensione nel <xref:System.Data.DataRowExtensions> e <xref:System.Data.DataTableExtensions> classi.</span><span class="sxs-lookup"><span data-stu-id="5301c-109">The [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] functionality is exposed primarily through the extension methods in the <xref:System.Data.DataRowExtensions> and <xref:System.Data.DataTableExtensions> classes.</span></span> [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] <span data-ttu-id="5301c-110">si basa sull'e Usa l'architettura ADO.NET esistente e non è destinato a sostituire ADO.NET nel codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5301c-110">builds on and uses the existing ADO.NET architecture, and is not meant to replace ADO.NET in application code.</span></span> <span data-ttu-id="5301c-111">Codice ADO.NET esistente continuerà a funzionare in un [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5301c-111">Existing ADO.NET code will continue to function in a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] application.</span></span> <span data-ttu-id="5301c-112">La relazione di [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] ADO.NET e i dati di archivio è illustrato nel diagramma seguente.</span><span class="sxs-lookup"><span data-stu-id="5301c-112">The relationship of [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] to ADO.NET and the data store is illustrated in the following diagram.</span></span>  
  
 ![Diagramma che mostra che LINQ to DataSet è basato sul provider ADO.NET.](./media/linq-to-dataset/linq-dataset-ado-dotnet-provider.gif)  
  
## <a name="in-this-section"></a><span data-ttu-id="5301c-114">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="5301c-114">In This Section</span></span>  
 [<span data-ttu-id="5301c-115">Introduzione</span><span class="sxs-lookup"><span data-stu-id="5301c-115">Getting Started</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
  
 [<span data-ttu-id="5301c-116">Guida per programmatori</span><span class="sxs-lookup"><span data-stu-id="5301c-116">Programming Guide</span></span>](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a><span data-ttu-id="5301c-117">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="5301c-117">Reference</span></span>  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a><span data-ttu-id="5301c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5301c-118">See also</span></span>

- [<span data-ttu-id="5301c-119">LINQ (Language-Integrated Query) - C#</span><span class="sxs-lookup"><span data-stu-id="5301c-119">Language-Integrated Query (LINQ) - C#</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="5301c-120">LINQ (Language-Integrated Query) - Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5301c-120">Language-Integrated Query (LINQ) - Visual Basic</span></span>](../../../visual-basic/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="5301c-121">LINQ e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5301c-121">LINQ and ADO.NET</span></span>](../../../../docs/framework/data/adonet/linq-and-ado-net.md)
- [<span data-ttu-id="5301c-122">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5301c-122">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)
