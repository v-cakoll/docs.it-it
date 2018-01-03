---
title: Esecuzione di query su dataset (LINQ to DataSet)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 3793417502d359a9d05899f6e1d4306aac7ca88b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="querying-datasets-linq-to-dataset"></a><span data-ttu-id="fab8f-102">Esecuzione di query su dataset (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="fab8f-102">Querying DataSets (LINQ to DataSet)</span></span>
<span data-ttu-id="fab8f-103">È possibile iniziare a eseguire query su un oggetto <xref:System.Data.DataSet> dopo averlo popolato con i dati.</span><span class="sxs-lookup"><span data-stu-id="fab8f-103">After a <xref:System.Data.DataSet> object has been populated with data, you can begin querying it.</span></span> <span data-ttu-id="fab8f-104">La formulazione di query con [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] è simile all'utilizzo di [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] su altre origini dati con supporto [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fab8f-104">Formulating queries with [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] is similar to using [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] against other [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-enabled data sources.</span></span> <span data-ttu-id="fab8f-105">Tenere tuttavia presente che quando si utilizza [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] esegue una query su un <xref:System.Data.DataSet> si esegue una query di un'enumerazione dell'oggetto <xref:System.Data.DataRow> oggetti, anziché un'enumerazione di un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="fab8f-105">Remember, however, that when you use [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] queries over a <xref:System.Data.DataSet> object you are querying an enumeration of <xref:System.Data.DataRow> objects, instead of an enumeration of a custom type.</span></span> <span data-ttu-id="fab8f-106">Ciò significa che è possibile utilizzare uno dei membri del <xref:System.Data.DataRow> classe il [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] query.</span><span class="sxs-lookup"><span data-stu-id="fab8f-106">This means that you can use any of the members of the <xref:System.Data.DataRow> class in your [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] queries.</span></span> <span data-ttu-id="fab8f-107">e creare query dettagliate e complesse.</span><span class="sxs-lookup"><span data-stu-id="fab8f-107">This lets you to create rich, complex queries.</span></span>  
  
 <span data-ttu-id="fab8f-108">Come con altre implementazioni di [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], è possibile creare [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query in due formati diversi: espressione sintassi delle query e sintassi di query basate su metodo.</span><span class="sxs-lookup"><span data-stu-id="fab8f-108">As with other implementations of [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], you can create [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] queries in two different forms: query expression syntax and method-based query syntax.</span></span> <span data-ttu-id="fab8f-109">Per ulteriori informazioni su questi due formati, vedere [Introduzione a LINQ](http://msdn.microsoft.com/en-us/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9).</span><span class="sxs-lookup"><span data-stu-id="fab8f-109">For more information about these two forms, see [Getting Started with LINQ](http://msdn.microsoft.com/en-us/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9).</span></span> <span data-ttu-id="fab8f-110">È possibile utilizzare la sintassi delle espressioni di query o la sintassi delle query basate su metodo per eseguire query su singole tabelle di <xref:System.Data.DataSet>, più tabelle di <xref:System.Data.DataSet> o tabelle di <xref:System.Data.DataSet> tipizzati.</span><span class="sxs-lookup"><span data-stu-id="fab8f-110">You can use query expression syntax or method-based query syntax to perform queries against single tables in a <xref:System.Data.DataSet>, against multiple tables in a <xref:System.Data.DataSet>, or against tables in a typed <xref:System.Data.DataSet>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fab8f-111">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="fab8f-111">In This Section</span></span>  
 [<span data-ttu-id="fab8f-112">Query su singola tabella</span><span class="sxs-lookup"><span data-stu-id="fab8f-112">Single-Table Queries</span></span>](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)  
 <span data-ttu-id="fab8f-113">Viene descritto come eseguire query su una singola tabella.</span><span class="sxs-lookup"><span data-stu-id="fab8f-113">Describes how to perform single-table queries.</span></span>  
  
 [<span data-ttu-id="fab8f-114">Query su tabella incrociata</span><span class="sxs-lookup"><span data-stu-id="fab8f-114">Cross-Table Queries</span></span>](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 <span data-ttu-id="fab8f-115">Viene descritto come eseguire query tra tabelle.</span><span class="sxs-lookup"><span data-stu-id="fab8f-115">Describes how to perform cross-table queries.</span></span>  
  
 [<span data-ttu-id="fab8f-116">Esecuzione di query su oggetti DataSet tipizzati</span><span class="sxs-lookup"><span data-stu-id="fab8f-116">Querying Typed DataSets</span></span>](../../../../docs/framework/data/adonet/querying-typed-datasets.md)  
 <span data-ttu-id="fab8f-117">Viene descritto come eseguire una query su oggetti <xref:System.Data.DataSet> tipizzati.</span><span class="sxs-lookup"><span data-stu-id="fab8f-117">Describes how to query typed <xref:System.Data.DataSet> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fab8f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fab8f-118">See Also</span></span>  
 [<span data-ttu-id="fab8f-119">Esempi di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="fab8f-119">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="fab8f-120">Caricamento di dati in un oggetto DataSet</span><span class="sxs-lookup"><span data-stu-id="fab8f-120">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
