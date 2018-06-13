---
title: Esplorazione di oggetti DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 202026a1-ec79-435e-b507-12a77f5011b2
ms.openlocfilehash: 3bd10694512e828354254588361cc009aac6602f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756368"
---
# <a name="navigating-datatables"></a><span data-ttu-id="b778b-102">Esplorazione di oggetti DataTable</span><span class="sxs-lookup"><span data-stu-id="b778b-102">Navigating DataTables</span></span>
<span data-ttu-id="b778b-103">Il tipo <xref:System.Data.DataTableReader> presenta il contenuto di uno o più oggetti <xref:System.Data.DataTable> sotto forma di uno o più set di risultati forward-only di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="b778b-103">The <xref:System.Data.DataTableReader> obtains the contents of one or more <xref:System.Data.DataTable> objects in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="b778b-104">Un tipo <xref:System.Data.DataTableReader> può contenere più set di risultati se viene creato tramite il metodo <xref:System.Data.DataSet.CreateDataReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="b778b-104">A <xref:System.Data.DataTableReader> may contain multiple result sets if it is created by using the <xref:System.Data.DataSet.CreateDataReader%2A> method.</span></span> <span data-ttu-id="b778b-105">Quando è presente più di un set di risultati, il metodo <xref:System.Data.DataTableReader.NextResult%2A> sposta il cursore al set di risultati successivo.</span><span class="sxs-lookup"><span data-stu-id="b778b-105">When there is more than one result set, the <xref:System.Data.DataTableReader.NextResult%2A> method advances the cursor to the next result set.</span></span> <span data-ttu-id="b778b-106">Questa proprietà è forward-only.</span><span class="sxs-lookup"><span data-stu-id="b778b-106">This is a forward-only process.</span></span> <span data-ttu-id="b778b-107">Non è possibile tornare a un set di risultati precedente.</span><span class="sxs-lookup"><span data-stu-id="b778b-107">It is not possible to return to a previous result set.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b778b-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="b778b-108">Example</span></span>  
 <span data-ttu-id="b778b-109">Nell'esempio seguente, il `TestConstructor` metodo crea due <xref:System.Data.DataTable> istanze.</span><span class="sxs-lookup"><span data-stu-id="b778b-109">In the following example, the `TestConstructor` method creates two <xref:System.Data.DataTable> instances.</span></span> <span data-ttu-id="b778b-110">Per illustrare questo costruttore per il <xref:System.Data.DataTableReader> (classe), l'esempio crea un nuovo **DataTableReader** basato su una matrice che contiene i due **DataTable**ed esegue un'operazione semplice, stampa il contenuto delle prime colonne nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="b778b-110">In order to demonstrate this constructor for the <xref:System.Data.DataTableReader> class, the sample creates a new **DataTableReader** based on an array that contains the two **DataTables**, and performs a simple operation, printing the contents from the first few columns to the console window.</span></span>  
  
 [!code-csharp[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b778b-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b778b-111">See Also</span></span>  
 [<span data-ttu-id="b778b-112">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="b778b-112">DataTableReaders</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)  
 [<span data-ttu-id="b778b-113">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="b778b-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
