---
title: Esecuzione di query su dataset tipizzati
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: fff678a54416e72f4be8c3fdfdcacec5a7d90af7
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="querying-typed-datasets"></a><span data-ttu-id="fa697-102">Esecuzione di query su dataset tipizzati</span><span class="sxs-lookup"><span data-stu-id="fa697-102">Querying Typed DataSets</span></span>
<span data-ttu-id="fa697-103">Se si conosce lo schema di <xref:System.Data.DataSet> in fase di progettazione dell'applicazione, è consigliabile usare <xref:System.Data.DataSet> tipizzati con [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa697-103">If the schema of the <xref:System.Data.DataSet> is known at application design time, we recommend that you use a typed <xref:System.Data.DataSet> when using [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="fa697-104">Un oggetto tipizzato <xref:System.Data.DataSet> è una classe che deriva da un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="fa697-104">A typed <xref:System.Data.DataSet> is a class that derives from a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="fa697-105">In quanto tale, tale oggetto eredita tutti i metodi, gli eventi e le proprietà di un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="fa697-105">As such, it inherits all the methods, events, and properties of a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="fa697-106">Inoltre, un oggetto tipizzato <xref:System.Data.DataSet> fornisce metodi fortemente tipizzati, proprietà ed eventi.</span><span class="sxs-lookup"><span data-stu-id="fa697-106">Additionally, a typed <xref:System.Data.DataSet> provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="fa697-107">È quindi possibile accedere a tabelle e colonne in base al nome, anziché usare metodi basati su raccolta.</span><span class="sxs-lookup"><span data-stu-id="fa697-107">This means that you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="fa697-108">Le query risultano quindi più semplici e più leggibili.</span><span class="sxs-lookup"><span data-stu-id="fa697-108">This makes queries simpler and more readable.</span></span> <span data-ttu-id="fa697-109">Per ulteriori informazioni, vedere [tipizzati](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="fa697-109">For more information, see [Typed DataSets](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span></span>  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="fa697-110">supporta inoltre l'esecuzione di query su un oggetto tipizzato <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="fa697-110"> also supports querying over a typed <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="fa697-111">Con un oggetto tipizzato <xref:System.Data.DataSet>, non è necessario utilizzare il metodo generico <xref:System.Data.DataRowExtensions.Field%2A> metodo o <xref:System.Data.DataRowExtensions.SetField%2A> metodo per accedere ai dati di colonna.</span><span class="sxs-lookup"><span data-stu-id="fa697-111">With a typed <xref:System.Data.DataSet>, you do not have to use the generic <xref:System.Data.DataRowExtensions.Field%2A> method or <xref:System.Data.DataRowExtensions.SetField%2A> method to access column data.</span></span>  <span data-ttu-id="fa697-112">I nomi delle proprietà sono disponibili in fase di compilazione perché le informazioni sul tipo è incluso nel <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="fa697-112">Property names are available at compile time because the type information is included in the <xref:System.Data.DataSet>.</span></span> [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="fa697-113">fornisce accesso ai valori di colonna come tipo corretto, in modo che gli errori di mancata corrispondenza di tipo vengono intercettati durante la compilazione del codice anziché in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fa697-113"> provides access to column values as the correct type, so that type mismatch errors are caught when the code is compiled instead of at run time.</span></span>  
  
 <span data-ttu-id="fa697-114">Prima di iniziare a eseguire query su un oggetto <xref:System.Data.DataSet> tipizzato, è necessario generare la classe usando Progettazione DataSet in [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa697-114">Before you can begin querying a typed <xref:System.Data.DataSet>, you must generate the class by using the DataSet Designer in [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].</span></span>  <span data-ttu-id="fa697-115">Per altre informazioni, vedere [Create and configure datasets](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio) (Creare e configurare set di dati).</span><span class="sxs-lookup"><span data-stu-id="fa697-115">For more information, see [Create and configure datasets](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa697-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="fa697-116">Example</span></span>  
 <span data-ttu-id="fa697-117">Nell'esempio seguente viene illustrata una query su un oggetto <xref:System.Data.DataSet> tipizzato.</span><span class="sxs-lookup"><span data-stu-id="fa697-117">The following example shows a query over a typed <xref:System.Data.DataSet>:</span></span>  
  
```csharp  
var query = from o in orders  
            where o.OnlineOrderFlag == true  
            select new { o.SalesOrderID,  
                         o.OrderDate,  
                         o.SalesOrderNumber };  
  
foreach(var order in query)   
{  
    Console.WriteLine("{0}\t{1:d}\t{2}",   
order.SalesOrderID,   
order.OrderDate,   
order.SalesOrderNumber);  
}  
```  
  
```vb  
Dim orders = ds.Tables("SalesOrderHeader")  
  
Dim query = _  
       From o In orders _  
       Where o.OnlineOrderFlag = True _  
       Select New {SalesOrderID := o.SalesOrderID, _  
                   OrderDate := o.OrderDate, _  
                   SalesOrderNumber := o.SalesOrderNumber}  
  
For Each Dim onlineOrder In query  
 Console.WriteLine("{0}\t{1:d}\t{2}", _  
 onlineOrder.SalesOrderID, _  
 onlineOrder.OrderDate, _  
 onlineOrder.SalesOrderNumber)  
Next  
```  
  
## <a name="see-also"></a><span data-ttu-id="fa697-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa697-118">See Also</span></span>  
 [<span data-ttu-id="fa697-119">Esecuzione di query su oggetti DataSet</span><span class="sxs-lookup"><span data-stu-id="fa697-119">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 [<span data-ttu-id="fa697-120">Query su tabella incrociata</span><span class="sxs-lookup"><span data-stu-id="fa697-120">Cross-Table Queries</span></span>](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 [<span data-ttu-id="fa697-121">Query su singola tabella</span><span class="sxs-lookup"><span data-stu-id="fa697-121">Single-Table Queries</span></span>](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)
