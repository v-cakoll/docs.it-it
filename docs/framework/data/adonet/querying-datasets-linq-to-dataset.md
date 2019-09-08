---
title: Esecuzione di query su dataset (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
ms.openlocfilehash: 79a9b320fbdbfecc3f7d531d992b1529873871a5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783040"
---
# <a name="querying-datasets-linq-to-dataset"></a><span data-ttu-id="35f37-102">Esecuzione di query su dataset (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="35f37-102">Querying DataSets (LINQ to DataSet)</span></span>
<span data-ttu-id="35f37-103">È possibile iniziare a eseguire query su un oggetto <xref:System.Data.DataSet> dopo averlo popolato con i dati.</span><span class="sxs-lookup"><span data-stu-id="35f37-103">After a <xref:System.Data.DataSet> object has been populated with data, you can begin querying it.</span></span> <span data-ttu-id="35f37-104">La formulazione di query con LINQ to DataSet è simile [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] all'utilizzo [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]di su altre origini dati abilitate.</span><span class="sxs-lookup"><span data-stu-id="35f37-104">Formulating queries with LINQ to DataSet is similar to using [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] against other [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-enabled data sources.</span></span> <span data-ttu-id="35f37-105">Tenere presente, tuttavia, che quando si [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] utilizzano query su <xref:System.Data.DataSet> un oggetto si esegue una query su un' <xref:System.Data.DataRow> enumerazione di oggetti, anziché un'enumerazione di un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="35f37-105">Remember, however, that when you use [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] queries over a <xref:System.Data.DataSet> object you are querying an enumeration of <xref:System.Data.DataRow> objects, instead of an enumeration of a custom type.</span></span> <span data-ttu-id="35f37-106">Ciò significa che è possibile usare qualsiasi membro della <xref:System.Data.DataRow> classe [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] nelle query.</span><span class="sxs-lookup"><span data-stu-id="35f37-106">This means that you can use any of the members of the <xref:System.Data.DataRow> class in your [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] queries.</span></span> <span data-ttu-id="35f37-107">e creare query dettagliate e complesse.</span><span class="sxs-lookup"><span data-stu-id="35f37-107">This lets you to create rich, complex queries.</span></span>  
  
 <span data-ttu-id="35f37-108">Come per le altre implementazioni [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]di, è possibile creare query LINQ to DataSet in due formati diversi, ovvero la sintassi delle espressioni di query e la sintassi delle query basate su metodo.</span><span class="sxs-lookup"><span data-stu-id="35f37-108">As with other implementations of [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], you can create LINQ to DataSet queries in two different forms: query expression syntax and method-based query syntax.</span></span> <span data-ttu-id="35f37-109">È possibile utilizzare la sintassi delle espressioni di query o la sintassi delle query basate su metodo per eseguire query su singole tabelle di <xref:System.Data.DataSet>, più tabelle di <xref:System.Data.DataSet> o tabelle di <xref:System.Data.DataSet> tipizzati.</span><span class="sxs-lookup"><span data-stu-id="35f37-109">You can use query expression syntax or method-based query syntax to perform queries against single tables in a <xref:System.Data.DataSet>, against multiple tables in a <xref:System.Data.DataSet>, or against tables in a typed <xref:System.Data.DataSet>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="35f37-110">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="35f37-110">In This Section</span></span>  
 [<span data-ttu-id="35f37-111">Query su singola tabella</span><span class="sxs-lookup"><span data-stu-id="35f37-111">Single-Table Queries</span></span>](single-table-queries-linq-to-dataset.md)  
 <span data-ttu-id="35f37-112">Viene descritto come eseguire query su una singola tabella.</span><span class="sxs-lookup"><span data-stu-id="35f37-112">Describes how to perform single-table queries.</span></span>  
  
 [<span data-ttu-id="35f37-113">Query su tabella incrociata</span><span class="sxs-lookup"><span data-stu-id="35f37-113">Cross-Table Queries</span></span>](cross-table-queries-linq-to-dataset.md)  
 <span data-ttu-id="35f37-114">Viene descritto come eseguire query tra tabelle.</span><span class="sxs-lookup"><span data-stu-id="35f37-114">Describes how to perform cross-table queries.</span></span>  
  
 [<span data-ttu-id="35f37-115">Esecuzione di query su oggetti DataSet tipizzati</span><span class="sxs-lookup"><span data-stu-id="35f37-115">Querying Typed DataSets</span></span>](querying-typed-datasets.md)  
 <span data-ttu-id="35f37-116">Viene descritto come eseguire una query su oggetti <xref:System.Data.DataSet> tipizzati.</span><span class="sxs-lookup"><span data-stu-id="35f37-116">Describes how to query typed <xref:System.Data.DataSet> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35f37-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35f37-117">See also</span></span>

- [<span data-ttu-id="35f37-118">Esempi di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="35f37-118">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="35f37-119">Caricamento di dati in un oggetto DataSet</span><span class="sxs-lookup"><span data-stu-id="35f37-119">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
