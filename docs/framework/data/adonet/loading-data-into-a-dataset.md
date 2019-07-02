---
title: Caricamento di dati in un dataset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: 26b77269b21e1b365f81746ba2df66d7df91677e
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504324"
---
# <a name="loading-data-into-a-dataset"></a>Caricamento di dati in un dataset
Oggetto <xref:System.Data.DataSet> oggetto debba essere inserito per primi prima di eseguire query su di esso con LINQ to DataSet. Sono disponibili diversi modi per popolare <xref:System.Data.DataSet>. Ad esempio, è possibile usare [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] per eseguire query sul database e caricare i risultati nel <xref:System.Data.DataSet>. Per altre informazioni, vedere [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).  
  
 Per caricare i dati in <xref:System.Data.DataSet>, è inoltre usare la classe <xref:System.Data.Common.DataAdapter> per recuperare i dati dal database, Questa procedura è illustrata nell'esempio riportato di seguito.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usato un oggetto <xref:System.Data.Common.DataAdapter> per eseguire una query sul database AdventureWorks relativa alle informazioni sulle vendite dell'anno 2002. I risultati vengono quindi caricati in un oggetto <xref:System.Data.DataSet>. Dopo il <xref:System.Data.DataSet> è stato popolato, è possibile scrivere query su di esso con LINQ to DataSet. Il `FillDataSet` metodo in questo esempio viene usato nelle query di esempio nella [LINQ to DataSet esempi](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md). Per altre informazioni, vedere [esecuzione di query su set di dati](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md).  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-overview.md)
- [Esecuzione di query su oggetti DataSet](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)
- [Esempi di LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
