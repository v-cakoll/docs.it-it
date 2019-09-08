---
title: Creazione di un oggetto DataReader
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
ms.openlocfilehash: 79cb2ce7ffae81aeba9aaca557e37ba566a8370c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784756"
---
# <a name="creating-a-datareader"></a><span data-ttu-id="a09a0-102">Creazione di un oggetto DataReader</span><span class="sxs-lookup"><span data-stu-id="a09a0-102">Creating a DataReader</span></span>
<span data-ttu-id="a09a0-103">Le classi <xref:System.Data.DataTable> e <xref:System.Data.DataSet> dispongono di un metodo <xref:System.Data.DataTable.CreateDataReader%2A> che restituisce il contenuto del tipo <xref:System.Data.DataTable> o della raccolta <xref:System.Data.DataSet> dell'oggetto <xref:System.Data.DataSet.Tables%2A> come uno o più set di risultati forward-only di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="a09a0-103">The <xref:System.Data.DataTable> and <xref:System.Data.DataSet> classes have a <xref:System.Data.DataTable.CreateDataReader%2A> method that returns the contents of the <xref:System.Data.DataTable> or the contents of the <xref:System.Data.DataSet> object's <xref:System.Data.DataSet.Tables%2A> collection as one or more read-only, forward-only result sets.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a09a0-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="a09a0-104">Example</span></span>  
 <span data-ttu-id="a09a0-105">Nell'applicazione console seguente viene creata un'istanza di <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="a09a0-105">The following console application creates a <xref:System.Data.DataTable> instance.</span></span> <span data-ttu-id="a09a0-106">Nell'esempio viene quindi passata la <xref:System.Data.DataTable> compilazione a una routine che chiama <xref:System.Data.DataTable.CreateDataReader%2A> il metodo, che scorre <xref:System.Data.DataTableReader>i risultati contenuti all'interno di.</span><span class="sxs-lookup"><span data-stu-id="a09a0-106">The example then passes the filled <xref:System.Data.DataTable> to a procedure that calls the <xref:System.Data.DataTable.CreateDataReader%2A> method, which iterates through the results contained within the <xref:System.Data.DataTableReader>.</span></span>  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 <span data-ttu-id="a09a0-107">Nell'esempio viene visualizzato il seguente output nella finestra della console:</span><span class="sxs-lookup"><span data-stu-id="a09a0-107">The example displays the following output in the console window:</span></span>  
  
```  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## <a name="see-also"></a><span data-ttu-id="a09a0-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a09a0-108">See also</span></span>

- <xref:System.Data.DataTable.CreateDataReader%2A>
- <xref:System.Data.DataSet.CreateDataReader%2A>
- [<span data-ttu-id="a09a0-109">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="a09a0-109">DataTableReaders</span></span>](datatablereaders.md)
- [<span data-ttu-id="a09a0-110">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a09a0-110">ADO.NET Overview</span></span>](../ado-net-overview.md)
