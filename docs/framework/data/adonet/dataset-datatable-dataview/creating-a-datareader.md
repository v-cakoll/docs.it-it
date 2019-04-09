---
title: Creazione di un oggetto DataReader
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
ms.openlocfilehash: 8932f393af58f2014f643c5b6ebd6dc7a127b7eb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122005"
---
# <a name="creating-a-datareader"></a><span data-ttu-id="509ee-102">Creazione di un oggetto DataReader</span><span class="sxs-lookup"><span data-stu-id="509ee-102">Creating a DataReader</span></span>
<span data-ttu-id="509ee-103">Le classi <xref:System.Data.DataTable> e <xref:System.Data.DataSet> dispongono di un metodo <xref:System.Data.DataTable.CreateDataReader%2A> che restituisce il contenuto del tipo <xref:System.Data.DataTable> o della raccolta <xref:System.Data.DataSet> dell'oggetto <xref:System.Data.DataSet.Tables%2A> come uno o più set di risultati forward-only di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="509ee-103">The <xref:System.Data.DataTable> and <xref:System.Data.DataSet> classes have a <xref:System.Data.DataTable.CreateDataReader%2A> method that returns the contents of the <xref:System.Data.DataTable> or the contents of the <xref:System.Data.DataSet> object's <xref:System.Data.DataSet.Tables%2A> collection as one or more read-only, forward-only result sets.</span></span>  
  
## <a name="example"></a><span data-ttu-id="509ee-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="509ee-104">Example</span></span>  
 <span data-ttu-id="509ee-105">Nell'applicazione console seguente viene creata un'istanza di <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="509ee-105">The following console application creates a <xref:System.Data.DataTable> instance.</span></span> <span data-ttu-id="509ee-106">Nell'esempio viene quindi compilato passato <xref:System.Data.DataTable> a una routine che chiama il <xref:System.Data.DataTable.CreateDataReader%2A> metodo, che scorre i risultati contenuti all'interno di <xref:System.Data.DataTableReader>.</span><span class="sxs-lookup"><span data-stu-id="509ee-106">The example then passes the filled <xref:System.Data.DataTable> to a procedure that calls the <xref:System.Data.DataTable.CreateDataReader%2A> method, which iterates through the results contained within the <xref:System.Data.DataTableReader>.</span></span>  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 <span data-ttu-id="509ee-107">Nell'esempio viene visualizzato il seguente output nella finestra della console:</span><span class="sxs-lookup"><span data-stu-id="509ee-107">The example displays the following output in the console window:</span></span>  
  
```  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## <a name="see-also"></a><span data-ttu-id="509ee-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="509ee-108">See also</span></span>

- <xref:System.Data.DataTable.CreateDataReader%2A>
- <xref:System.Data.DataSet.CreateDataReader%2A>
- [<span data-ttu-id="509ee-109">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="509ee-109">DataTableReaders</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)
- [<span data-ttu-id="509ee-110">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="509ee-110">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
