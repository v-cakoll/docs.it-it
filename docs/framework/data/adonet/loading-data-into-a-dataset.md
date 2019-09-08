---
title: Caricamento di dati in un dataset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: 53f0f5a589a0033c9612f0465dff090ab04e3fc4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794952"
---
# <a name="loading-data-into-a-dataset"></a>Caricamento di dati in un dataset
Prima <xref:System.Data.DataSet> di poter eseguire una query su di esso con LINQ to DataSet, è necessario innanzitutto popolare un oggetto. Sono disponibili diversi modi per popolare <xref:System.Data.DataSet>. Ad esempio, è possibile utilizzare [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] per eseguire una query sul database e caricare i risultati <xref:System.Data.DataSet>in. Per altre informazioni, vedere [LINQ to SQL](./sql/linq/index.md).  
  
 Per caricare i dati in <xref:System.Data.DataSet>, è inoltre usare la classe <xref:System.Data.Common.DataAdapter> per recuperare i dati dal database, Questa procedura è illustrata nell'esempio riportato di seguito.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usato un oggetto <xref:System.Data.Common.DataAdapter> per eseguire una query sul database AdventureWorks relativa alle informazioni sulle vendite dell'anno 2002. I risultati vengono quindi caricati in un oggetto <xref:System.Data.DataSet>. <xref:System.Data.DataSet> Una volta popolato, è possibile scrivere query su di esso utilizzando LINQ to DataSet. Il `FillDataSet` metodo in questo esempio viene usato nelle query di esempio in [LINQ to DataSet esempi](linq-to-dataset-examples.md). Per ulteriori informazioni, vedere [esecuzione di query sui set](querying-datasets-linq-to-dataset.md)di dati.  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di LINQ to DataSet](linq-to-dataset-overview.md)
- [Esecuzione di query su oggetti DataSet](querying-datasets-linq-to-dataset.md)
- [Esempi di LINQ to DataSet](linq-to-dataset-examples.md)
