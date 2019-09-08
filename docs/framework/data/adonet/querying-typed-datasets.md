---
title: Esecuzione di query su dataset tipizzati
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
ms.openlocfilehash: 55714c4dae73cd17a849cc35681797dfa4266e3b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782973"
---
# <a name="query-typed-datasets"></a><span data-ttu-id="70c1a-102">Eseguire query su DataSet tipizzati</span><span class="sxs-lookup"><span data-stu-id="70c1a-102">Query typed DataSets</span></span>

<span data-ttu-id="70c1a-103">Se lo schema di <xref:System.Data.DataSet> è noto in fase di progettazione dell'applicazione, è consigliabile usare un oggetto tipizzato <xref:System.Data.DataSet> quando si usa LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="70c1a-103">If the schema of the <xref:System.Data.DataSet> is known at application design time, we recommend that you use a typed <xref:System.Data.DataSet> when using LINQ to DataSet.</span></span> <span data-ttu-id="70c1a-104">Un oggetto <xref:System.Data.DataSet> tipizzato è una classe che deriva da <xref:System.Data.DataSet>un oggetto.</span><span class="sxs-lookup"><span data-stu-id="70c1a-104">A typed <xref:System.Data.DataSet> is a class that derives from a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="70c1a-105">In quanto tale, tale oggetto eredita tutti i metodi, gli eventi e le proprietà di un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="70c1a-105">As such, it inherits all the methods, events, and properties of a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="70c1a-106">Un oggetto tipizzato <xref:System.Data.DataSet> fornisce inoltre metodi, eventi e proprietà fortemente tipizzati.</span><span class="sxs-lookup"><span data-stu-id="70c1a-106">Additionally, a typed <xref:System.Data.DataSet> provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="70c1a-107">È quindi possibile accedere a tabelle e colonne in base al nome, anziché usare metodi basati su raccolta.</span><span class="sxs-lookup"><span data-stu-id="70c1a-107">This means that you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="70c1a-108">Le query risultano quindi più semplici e più leggibili.</span><span class="sxs-lookup"><span data-stu-id="70c1a-108">This makes queries simpler and more readable.</span></span> <span data-ttu-id="70c1a-109">Per altre informazioni, vedere [DataSet tipizzati](./dataset-datatable-dataview/typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="70c1a-109">For more information, see [Typed DataSets](./dataset-datatable-dataview/typed-datasets.md).</span></span>

<span data-ttu-id="70c1a-110">LINQ to DataSet supporta anche l'esecuzione di query su <xref:System.Data.DataSet>un oggetto tipizzato.</span><span class="sxs-lookup"><span data-stu-id="70c1a-110">LINQ to DataSet also supports querying over a typed <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="70c1a-111">Con un oggetto <xref:System.Data.DataSet>tipizzato, non è necessario usare il metodo <xref:System.Data.DataRowExtensions.Field%2A> o <xref:System.Data.DataRowExtensions.SetField%2A> il metodo generico per accedere ai dati della colonna.</span><span class="sxs-lookup"><span data-stu-id="70c1a-111">With a typed <xref:System.Data.DataSet>, you do not have to use the generic <xref:System.Data.DataRowExtensions.Field%2A> method or <xref:System.Data.DataRowExtensions.SetField%2A> method to access column data.</span></span> <span data-ttu-id="70c1a-112">I nomi delle proprietà sono disponibili in fase di compilazione perché le informazioni sul tipo <xref:System.Data.DataSet>sono incluse in.</span><span class="sxs-lookup"><span data-stu-id="70c1a-112">Property names are available at compile time because the type information is included in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="70c1a-113">LINQ to DataSet fornisce l'accesso ai valori di colonna come tipo corretto, in modo che vengano rilevati errori di mancata corrispondenza del tipo quando il codice viene compilato anziché in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="70c1a-113">LINQ to DataSet provides access to column values as the correct type, so that type mismatch errors are caught when the code is compiled instead of at run time.</span></span>

<span data-ttu-id="70c1a-114">Prima di iniziare a eseguire query su un <xref:System.Data.DataSet>oggetto tipizzato, è necessario generare la classe usando **Progettazione DataSet** in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="70c1a-114">Before you can begin querying a typed <xref:System.Data.DataSet>, you must generate the class by using the **DataSet Designer** in Visual Studio.</span></span> <span data-ttu-id="70c1a-115">Per altre informazioni, vedere [creare e configurare set](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio)di dati.</span><span class="sxs-lookup"><span data-stu-id="70c1a-115">For more information, see [Create and configure DataSets](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).</span></span>

## <a name="example"></a><span data-ttu-id="70c1a-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="70c1a-116">Example</span></span>

<span data-ttu-id="70c1a-117">Nell'esempio seguente viene illustrata una query su un oggetto <xref:System.Data.DataSet> tipizzato.</span><span class="sxs-lookup"><span data-stu-id="70c1a-117">The following example shows a query over a typed <xref:System.Data.DataSet>:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="70c1a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70c1a-118">See also</span></span>

- [<span data-ttu-id="70c1a-119">Esecuzione di query su oggetti DataSet</span><span class="sxs-lookup"><span data-stu-id="70c1a-119">Querying DataSets</span></span>](querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="70c1a-120">Query su tabella incrociata</span><span class="sxs-lookup"><span data-stu-id="70c1a-120">Cross-Table Queries</span></span>](cross-table-queries-linq-to-dataset.md)
- [<span data-ttu-id="70c1a-121">Query su singola tabella</span><span class="sxs-lookup"><span data-stu-id="70c1a-121">Single-Table Queries</span></span>](single-table-queries-linq-to-dataset.md)
