---
title: Guida per programmatori (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: 977aedd7-0084-46a0-b56f-345787a55da1
ms.openlocfilehash: c971f0a92829df40a14631aaff353a268f277f11
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783198"
---
# <a name="programming-guide-linq-to-dataset"></a><span data-ttu-id="91030-102">Guida per programmatori (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="91030-102">Programming Guide (LINQ to DataSet)</span></span>
<span data-ttu-id="91030-103">In questa sezione vengono fornite informazioni concettuali ed esempi per la programmazione con LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="91030-103">This section provides conceptual information and examples for programming with LINQ to DataSet.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="91030-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="91030-104">In This Section</span></span>  
 [<span data-ttu-id="91030-105">Query in LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="91030-105">Queries in LINQ to DataSet</span></span>](queries-in-linq-to-dataset.md)  
 <span data-ttu-id="91030-106">Vengono fornite informazioni su come scrivere LINQ to DataSet query.</span><span class="sxs-lookup"><span data-stu-id="91030-106">Provides information about how to write LINQ to DataSet queries.</span></span>  
  
 [<span data-ttu-id="91030-107">Esecuzione di query su oggetti DataSet</span><span class="sxs-lookup"><span data-stu-id="91030-107">Querying DataSets</span></span>](querying-datasets-linq-to-dataset.md)  
 <span data-ttu-id="91030-108">Viene descritto come eseguire una query su oggetti <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="91030-108">Describes how to query <xref:System.Data.DataSet> objects.</span></span>  
  
 [<span data-ttu-id="91030-109">Confronto di DataRows</span><span class="sxs-lookup"><span data-stu-id="91030-109">Comparing DataRows</span></span>](comparing-datarows-linq-to-dataset.md)  
 <span data-ttu-id="91030-110">Viene descritto come usare l'oggetto <xref:System.Data.DataRowComparer> per confrontare righe di dati.</span><span class="sxs-lookup"><span data-stu-id="91030-110">Describes how to use the <xref:System.Data.DataRowComparer> object to compare data rows.</span></span>  
  
 [<span data-ttu-id="91030-111">Creazione di un oggetto DataTable da una query</span><span class="sxs-lookup"><span data-stu-id="91030-111">Creating a DataTable From a Query</span></span>](creating-a-datatable-from-a-query-linq-to-dataset.md)  
 <span data-ttu-id="91030-112">Vengono fornite informazioni sulla creazione <xref:System.Data.DataTable> di un oggetto da una query LINQ to DataSet <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> tramite il metodo.</span><span class="sxs-lookup"><span data-stu-id="91030-112">Provides information about creating a <xref:System.Data.DataTable> from a LINQ to DataSet query by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [<span data-ttu-id="91030-113">Procedura: Implementare CopyToDataTable\<t > in cui il tipo generico t non è un DataRow</span><span class="sxs-lookup"><span data-stu-id="91030-113">How to: Implement CopyToDataTable\<T> Where the Generic Type T Is Not a DataRow</span></span>](implement-copytodatatable-where-type-not-a-datarow.md)  
 <span data-ttu-id="91030-114">Viene descritto come implementare un metodo `CopyToDataTable<T>` personalizzato in cui il parametro generico T non è di tipo <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="91030-114">Describes how to implement a custom `CopyToDataTable<T>` method where the generic parameter T is not of type <xref:System.Data.DataRow>.</span></span>  
  
 [<span data-ttu-id="91030-115">Metodi generici Field e SetField</span><span class="sxs-lookup"><span data-stu-id="91030-115">Generic Field and SetField Methods</span></span>](generic-field-and-setfield-methods-linq-to-dataset.md)  
 <span data-ttu-id="91030-116">Vengono fornite informazioni sui metodi <xref:System.Data.DataRowExtensions.Field%2A> e <xref:System.Data.DataRowExtensions.SetField%2A> generici.</span><span class="sxs-lookup"><span data-stu-id="91030-116">Provides information about the generic <xref:System.Data.DataRowExtensions.Field%2A> and <xref:System.Data.DataRowExtensions.SetField%2A> methods.</span></span>  
  
 [<span data-ttu-id="91030-117">Data binding e LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="91030-117">Data Binding and LINQ to DataSet</span></span>](data-binding-and-linq-to-dataset.md)  
 <span data-ttu-id="91030-118">Viene descritto il processo di associazione dati usando l'oggetto <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="91030-118">Describes databinding using the <xref:System.Data.DataView> object.</span></span>  
  
 [<span data-ttu-id="91030-119">Debug di query di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="91030-119">Debugging LINQ to DataSet Queries</span></span>](debugging-linq-to-dataset-queries.md)  
 <span data-ttu-id="91030-120">Vengono fornite informazioni sul debug e la risoluzione dei problemi relativi alle query LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="91030-120">Provides information about debugging and troubleshooting LINQ to DataSet queries.</span></span>  
  
 [<span data-ttu-id="91030-121">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="91030-121">Security</span></span>](security-linq-to-dataset.md)  
 <span data-ttu-id="91030-122">Vengono descritti i problemi di sicurezza in LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="91030-122">Describes security issues in LINQ to DataSet.</span></span>  
  
 [<span data-ttu-id="91030-123">Esempi di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="91030-123">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)  
 <span data-ttu-id="91030-124">Vengono forniti esempi di query in cui vengono usati operatori [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="91030-124">Provides query examples that use the [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] operators.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="91030-125">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="91030-125">Reference</span></span>  
 <xref:System.Data.DataRowComparer>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataView>  
  
## <a name="see-also"></a><span data-ttu-id="91030-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91030-126">See also</span></span>

- [<span data-ttu-id="91030-127">LINQ e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="91030-127">LINQ and ADO.NET</span></span>](linq-and-ado-net.md)
- [<span data-ttu-id="91030-128">LINQ (Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="91030-128">Language Integrated Query (LINQ)</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
