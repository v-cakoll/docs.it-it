---
title: Creazione di un oggetto DataReader
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
ms.openlocfilehash: d3c20fa4394b09e9ceec332d430ed638166bed8e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491663"
---
# <a name="creating-a-datareader"></a>Creazione di un oggetto DataReader
Le classi <xref:System.Data.DataTable> e <xref:System.Data.DataSet> dispongono di un metodo <xref:System.Data.DataTable.CreateDataReader%2A> che restituisce il contenuto del tipo <xref:System.Data.DataTable> o della raccolta <xref:System.Data.DataSet> dell'oggetto <xref:System.Data.DataSet.Tables%2A> come uno o più set di risultati forward-only di sola lettura.  
  
## <a name="example"></a>Esempio  
 Nell'applicazione console seguente viene creata un'istanza di <xref:System.Data.DataTable>. Nell'esempio viene quindi compilato passato <xref:System.Data.DataTable> a una routine che chiama il <xref:System.Data.DataTable.CreateDataReader%2A> metodo, che scorre i risultati contenuti all'interno di <xref:System.Data.DataTableReader>.  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 Nell'esempio viene visualizzato il seguente output nella finestra della console:  
  
```  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Data.DataTable.CreateDataReader%2A>
- <xref:System.Data.DataSet.CreateDataReader%2A>
- [DataTableReader](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
