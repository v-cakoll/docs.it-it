---
title: Esecuzione di query su dataset tipizzati
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
ms.openlocfilehash: d956fd5f07c108146d20623bcf811266380c132c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43739646"
---
# <a name="query-typed-datasets"></a><span data-ttu-id="a9b87-102">Eseguire query sui set di dati tipizzati</span><span class="sxs-lookup"><span data-stu-id="a9b87-102">Query typed DataSets</span></span>

<span data-ttu-id="a9b87-103">Se lo schema del <xref:System.Data.DataSet> è noto in fase di progettazione dell'applicazione, è consigliabile usare un oggetto tipizzato <xref:System.Data.DataSet> quando si usa LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="a9b87-103">If the schema of the <xref:System.Data.DataSet> is known at application design time, we recommend that you use a typed <xref:System.Data.DataSet> when using LINQ to DataSet.</span></span> <span data-ttu-id="a9b87-104">Un oggetto tipizzato <xref:System.Data.DataSet> è una classe che deriva da un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="a9b87-104">A typed <xref:System.Data.DataSet> is a class that derives from a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="a9b87-105">In quanto tale, tale oggetto eredita tutti i metodi, gli eventi e le proprietà di un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="a9b87-105">As such, it inherits all the methods, events, and properties of a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="a9b87-106">Inoltre, un oggetto tipizzato <xref:System.Data.DataSet> fornisce metodi fortemente tipizzati, proprietà ed eventi.</span><span class="sxs-lookup"><span data-stu-id="a9b87-106">Additionally, a typed <xref:System.Data.DataSet> provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="a9b87-107">È quindi possibile accedere a tabelle e colonne in base al nome, anziché usare metodi basati su raccolta.</span><span class="sxs-lookup"><span data-stu-id="a9b87-107">This means that you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="a9b87-108">Le query risultano quindi più semplici e più leggibili.</span><span class="sxs-lookup"><span data-stu-id="a9b87-108">This makes queries simpler and more readable.</span></span> <span data-ttu-id="a9b87-109">Per altre informazioni, vedere [dataset tipizzati](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="a9b87-109">For more information, see [Typed DataSets](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span></span>

<span data-ttu-id="a9b87-110">LINQ to DataSet supporta anche l'esecuzione di query su un oggetto tipizzato <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="a9b87-110">LINQ to DataSet also supports querying over a typed <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="a9b87-111">Con un oggetto tipizzato <xref:System.Data.DataSet>, non è necessario utilizzare il tipo generico <xref:System.Data.DataRowExtensions.Field%2A> metodo o <xref:System.Data.DataRowExtensions.SetField%2A> metodo per accedere ai dati di colonna.</span><span class="sxs-lookup"><span data-stu-id="a9b87-111">With a typed <xref:System.Data.DataSet>, you do not have to use the generic <xref:System.Data.DataRowExtensions.Field%2A> method or <xref:System.Data.DataRowExtensions.SetField%2A> method to access column data.</span></span> <span data-ttu-id="a9b87-112">I nomi delle proprietà sono disponibili in fase di compilazione perché le informazioni sul tipo è incluso nel <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="a9b87-112">Property names are available at compile time because the type information is included in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="a9b87-113">LINQ to DataSet fornisce accesso ai valori di colonna con il tipo corretto, in modo che gli errori di mancata corrispondenza di tipo vengono intercettati durante la compilazione del codice anziché in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a9b87-113">LINQ to DataSet provides access to column values as the correct type, so that type mismatch errors are caught when the code is compiled instead of at run time.</span></span>

<span data-ttu-id="a9b87-114">Prima di iniziare l'esecuzione di query tipizzati <xref:System.Data.DataSet>, è necessario generare la classe usando il **Progettazione DataSet** in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a9b87-114">Before you can begin querying a typed <xref:System.Data.DataSet>, you must generate the class by using the **DataSet Designer** in Visual Studio.</span></span> <span data-ttu-id="a9b87-115">Per altre informazioni, vedere [creare e configurare i set di dati](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="a9b87-115">For more information, see [Create and configure DataSets](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).</span></span>

## <a name="example"></a><span data-ttu-id="a9b87-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="a9b87-116">Example</span></span>

<span data-ttu-id="a9b87-117">Nell'esempio seguente viene illustrata una query su un oggetto <xref:System.Data.DataSet> tipizzato.</span><span class="sxs-lookup"><span data-stu-id="a9b87-117">The following example shows a query over a typed <xref:System.Data.DataSet>:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a9b87-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9b87-118">See also</span></span>

- [<span data-ttu-id="a9b87-119">Esecuzione di query su oggetti DataSet</span><span class="sxs-lookup"><span data-stu-id="a9b87-119">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="a9b87-120">Query su tabella incrociata</span><span class="sxs-lookup"><span data-stu-id="a9b87-120">Cross-Table Queries</span></span>](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)
- [<span data-ttu-id="a9b87-121">Query su singola tabella</span><span class="sxs-lookup"><span data-stu-id="a9b87-121">Single-Table Queries</span></span>](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)
