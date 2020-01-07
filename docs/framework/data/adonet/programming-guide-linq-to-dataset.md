---
title: Guida per programmatori (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: 977aedd7-0084-46a0-b56f-345787a55da1
ms.openlocfilehash: dc13af06cf6c439d739d76904f206ebc50ba3187
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634807"
---
# <a name="programming-guide-linq-to-dataset"></a><span data-ttu-id="8a54b-102">Guida per programmatori (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="8a54b-102">Programming Guide (LINQ to DataSet)</span></span>
<span data-ttu-id="8a54b-103">In questa sezione vengono fornite informazioni concettuali ed esempi per la programmazione con LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="8a54b-103">This section provides conceptual information and examples for programming with LINQ to DataSet.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8a54b-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="8a54b-104">In This Section</span></span>  
 [<span data-ttu-id="8a54b-105">Query in LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="8a54b-105">Queries in LINQ to DataSet</span></span>](queries-in-linq-to-dataset.md)  
 <span data-ttu-id="8a54b-106">Vengono fornite informazioni su come scrivere LINQ to DataSet query.</span><span class="sxs-lookup"><span data-stu-id="8a54b-106">Provides information about how to write LINQ to DataSet queries.</span></span>  
  
 [<span data-ttu-id="8a54b-107">Esecuzione di query su oggetti DataSet</span><span class="sxs-lookup"><span data-stu-id="8a54b-107">Querying DataSets</span></span>](querying-datasets-linq-to-dataset.md)  
 <span data-ttu-id="8a54b-108">Viene descritto come eseguire una query su oggetti <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="8a54b-108">Describes how to query <xref:System.Data.DataSet> objects.</span></span>  
  
 [<span data-ttu-id="8a54b-109">Confronto di DataRows</span><span class="sxs-lookup"><span data-stu-id="8a54b-109">Comparing DataRows</span></span>](comparing-datarows-linq-to-dataset.md)  
 <span data-ttu-id="8a54b-110">Viene descritto come usare l'oggetto <xref:System.Data.DataRowComparer> per confrontare righe di dati.</span><span class="sxs-lookup"><span data-stu-id="8a54b-110">Describes how to use the <xref:System.Data.DataRowComparer> object to compare data rows.</span></span>  
  
 [<span data-ttu-id="8a54b-111">Creazione di un oggetto DataTable da una query</span><span class="sxs-lookup"><span data-stu-id="8a54b-111">Creating a DataTable From a Query</span></span>](creating-a-datatable-from-a-query-linq-to-dataset.md)  
 <span data-ttu-id="8a54b-112">Vengono fornite informazioni sulla creazione di un <xref:System.Data.DataTable> da una query LINQ to DataSet utilizzando il metodo <xref:System.Data.DataTableExtensions.CopyToDataTable%2A>.</span><span class="sxs-lookup"><span data-stu-id="8a54b-112">Provides information about creating a <xref:System.Data.DataTable> from a LINQ to DataSet query by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [<span data-ttu-id="8a54b-113">Procedura: implementare CopyToDataTable\<T > in cui il tipo generico T non è un DataRow</span><span class="sxs-lookup"><span data-stu-id="8a54b-113">How to: Implement CopyToDataTable\<T> Where the Generic Type T Is Not a DataRow</span></span>](implement-copytodatatable-where-type-not-a-datarow.md)  
 <span data-ttu-id="8a54b-114">Viene descritto come implementare un metodo `CopyToDataTable<T>` personalizzato in cui il parametro generico T non è di tipo <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="8a54b-114">Describes how to implement a custom `CopyToDataTable<T>` method where the generic parameter T is not of type <xref:System.Data.DataRow>.</span></span>  
  
 [<span data-ttu-id="8a54b-115">Metodi generici Field e SetField</span><span class="sxs-lookup"><span data-stu-id="8a54b-115">Generic Field and SetField Methods</span></span>](generic-field-and-setfield-methods-linq-to-dataset.md)  
 <span data-ttu-id="8a54b-116">Vengono fornite informazioni sui metodi <xref:System.Data.DataRowExtensions.Field%2A> e <xref:System.Data.DataRowExtensions.SetField%2A> generici.</span><span class="sxs-lookup"><span data-stu-id="8a54b-116">Provides information about the generic <xref:System.Data.DataRowExtensions.Field%2A> and <xref:System.Data.DataRowExtensions.SetField%2A> methods.</span></span>  
  
 [<span data-ttu-id="8a54b-117">Data binding e LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="8a54b-117">Data Binding and LINQ to DataSet</span></span>](data-binding-and-linq-to-dataset.md)  
 <span data-ttu-id="8a54b-118">Viene descritto il processo di associazione dati usando l'oggetto <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="8a54b-118">Describes databinding using the <xref:System.Data.DataView> object.</span></span>  
  
 [<span data-ttu-id="8a54b-119">Debug di query di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="8a54b-119">Debugging LINQ to DataSet Queries</span></span>](debugging-linq-to-dataset-queries.md)  
 <span data-ttu-id="8a54b-120">Vengono fornite informazioni sul debug e la risoluzione dei problemi relativi alle query LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="8a54b-120">Provides information about debugging and troubleshooting LINQ to DataSet queries.</span></span>  
  
 [<span data-ttu-id="8a54b-121">Security</span><span class="sxs-lookup"><span data-stu-id="8a54b-121">Security</span></span>](security-linq-to-dataset.md)  
 <span data-ttu-id="8a54b-122">Vengono descritti i problemi di sicurezza in LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="8a54b-122">Describes security issues in LINQ to DataSet.</span></span>  
  
 [<span data-ttu-id="8a54b-123">Esempi di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="8a54b-123">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)  
 <span data-ttu-id="8a54b-124">Vengono forniti esempi di query in cui vengono utilizzati operatori LINQ.</span><span class="sxs-lookup"><span data-stu-id="8a54b-124">Provides query examples that use the LINQ operators.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8a54b-125">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="8a54b-125">Reference</span></span>  
 <xref:System.Data.DataRowComparer>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataView>  
  
## <a name="see-also"></a><span data-ttu-id="8a54b-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a54b-126">See also</span></span>

- [<span data-ttu-id="8a54b-127">LINQ e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8a54b-127">LINQ and ADO.NET</span></span>](linq-and-ado-net.md)
- [<span data-ttu-id="8a54b-128">LINQ (Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="8a54b-128">Language Integrated Query (LINQ)</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
