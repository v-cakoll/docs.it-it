---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: 4995512336ee9eb6e33df011757ed533db57e76e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783781"
---
# <a name="linq-to-dataset"></a><span data-ttu-id="b43c5-102">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="b43c5-102">LINQ to DataSet</span></span>
<span data-ttu-id="b43c5-103">LINQ to DataSet semplifica e velocizza l'esecuzione di query sui dati memorizzati nella cache <xref:System.Data.DataSet> in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="b43c5-103">LINQ to DataSet makes it easier and faster to query over data cached in a <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="b43c5-104">In particolare, LINQ to DataSet semplifica l'esecuzione di query consentendo agli sviluppatori di scrivere query dal linguaggio di programmazione stesso, anziché usando un linguaggio di query distinto.</span><span class="sxs-lookup"><span data-stu-id="b43c5-104">Specifically, LINQ to DataSet simplifies querying by enabling developers to write queries from the programming language itself, instead of by using a separate query language.</span></span> <span data-ttu-id="b43c5-105">Ciò è particolarmente utile per gli sviluppatori di Visual Studio, che ora possono sfruttare il controllo della sintassi in fase di compilazione, la tipizzazione statica e il supporto IntelliSense fornito da Visual Studio nelle query.</span><span class="sxs-lookup"><span data-stu-id="b43c5-105">This is especially useful for Visual Studio developers, who can now take advantage of the compile-time syntax checking, static typing, and IntelliSense support provided by the Visual Studio in their queries.</span></span>  
  
 <span data-ttu-id="b43c5-106">LINQ to DataSet può essere utilizzato anche per eseguire query su dati che sono stati consolidati da una o più origini dati.</span><span class="sxs-lookup"><span data-stu-id="b43c5-106">LINQ to DataSet can also be used to query over data that has been consolidated from one or more data sources.</span></span> <span data-ttu-id="b43c5-107">In tal modo sono possibili molti scenari in cui è necessario rappresentare e gestire i dati con flessibilità, ad esempio per le query su dati aggregati localmente e la memorizzazione nella cache di livello intermedio nelle applicazioni Web.</span><span class="sxs-lookup"><span data-stu-id="b43c5-107">This enables many scenarios that require flexibility in how data is represented and handled, such as querying locally aggregated data and middle-tier caching in Web applications.</span></span> <span data-ttu-id="b43c5-108">In particolare, questo tipo di modifiche sono richieste nelle applicazioni generiche per la creazione di rapporti, di analisi e di Business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="b43c5-108">In particular, generic reporting, analysis, and business intelligence applications require this method of manipulation.</span></span>  
  
 <span data-ttu-id="b43c5-109">La funzionalità LINQ to DataSet viene esposta principalmente tramite i metodi di estensione nelle <xref:System.Data.DataRowExtensions> classi <xref:System.Data.DataTableExtensions> e.</span><span class="sxs-lookup"><span data-stu-id="b43c5-109">The LINQ to DataSet functionality is exposed primarily through the extension methods in the <xref:System.Data.DataRowExtensions> and <xref:System.Data.DataTableExtensions> classes.</span></span> <span data-ttu-id="b43c5-110">LINQ to DataSet si basa su e usa l'architettura ADO.NET esistente e non è destinata a sostituire ADO.NET nel codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b43c5-110">LINQ to DataSet builds on and uses the existing ADO.NET architecture, and is not meant to replace ADO.NET in application code.</span></span> <span data-ttu-id="b43c5-111">Il codice ADO.NET esistente continuerà a funzionare in un'applicazione LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="b43c5-111">Existing ADO.NET code will continue to function in a LINQ to DataSet application.</span></span> <span data-ttu-id="b43c5-112">Il diagramma seguente illustra la relazione tra LINQ to DataSet e ADO.NET e l'archivio dati.</span><span class="sxs-lookup"><span data-stu-id="b43c5-112">The relationship of LINQ to DataSet to ADO.NET and the data store is illustrated in the following diagram.</span></span>  
  
 ![Diagramma che mostra che LINQ to DataSet è basato sul provider ADO.NET.](./media/linq-to-dataset/linq-dataset-ado-dotnet-provider.gif)  
  
## <a name="in-this-section"></a><span data-ttu-id="b43c5-114">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="b43c5-114">In This Section</span></span>  
 [<span data-ttu-id="b43c5-115">Introduzione</span><span class="sxs-lookup"><span data-stu-id="b43c5-115">Getting Started</span></span>](getting-started-linq-to-dataset.md)  
  
 [<span data-ttu-id="b43c5-116">Guida per programmatori</span><span class="sxs-lookup"><span data-stu-id="b43c5-116">Programming Guide</span></span>](programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a><span data-ttu-id="b43c5-117">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="b43c5-117">Reference</span></span>  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a><span data-ttu-id="b43c5-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b43c5-118">See also</span></span>

- [<span data-ttu-id="b43c5-119">LINQ (Language-Integrated Query) - C#</span><span class="sxs-lookup"><span data-stu-id="b43c5-119">Language-Integrated Query (LINQ) - C#</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="b43c5-120">LINQ (Language-Integrated Query) - Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b43c5-120">Language-Integrated Query (LINQ) - Visual Basic</span></span>](../../../visual-basic/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="b43c5-121">LINQ e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b43c5-121">LINQ and ADO.NET</span></span>](linq-and-ado-net.md)
- [<span data-ttu-id="b43c5-122">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b43c5-122">ADO.NET</span></span>](index.md)
