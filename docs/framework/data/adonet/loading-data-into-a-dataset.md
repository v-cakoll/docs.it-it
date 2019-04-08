---
title: Caricamento di dati in un dataset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: cb5578d790e5d3f54f75f964bb3288d861c9d7c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074053"
---
# <a name="loading-data-into-a-dataset"></a>Caricamento di dati in un dataset
Per poter eseguire query su un oggetto <xref:System.Data.DataSet> con [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], è prima necessario popolarlo. Sono disponibili diversi modi per popolare <xref:System.Data.DataSet>. Ad esempio, è possibile usare [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] per eseguire query sul database e caricare i risultati nel <xref:System.Data.DataSet>. Per altre informazioni, vedere [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).  
  
 Per caricare i dati in <xref:System.Data.DataSet>, è inoltre usare la classe <xref:System.Data.Common.DataAdapter> per recuperare i dati dal database, Questa procedura è illustrata nell'esempio riportato di seguito.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usato un oggetto <xref:System.Data.Common.DataAdapter> per eseguire una query sul database AdventureWorks relativa alle informazioni sulle vendite dell'anno 2002. I risultati vengono quindi caricati in un oggetto <xref:System.Data.DataSet>. Dopo aver popolato <xref:System.Data.DataSet>, è possibile scrivere query da eseguire su di esso con [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]. Il `FillDataSet` metodo in questo esempio viene usato nelle query di esempio nella [LINQ to DataSet esempi](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md). Per altre informazioni, vedere [esecuzione di query su set di dati](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md).  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari su LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-overview.md)
- [Esecuzione di query su oggetti DataSet](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)
- [Esempi di LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
