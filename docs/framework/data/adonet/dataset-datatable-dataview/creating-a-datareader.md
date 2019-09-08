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
# <a name="creating-a-datareader"></a>Creazione di un oggetto DataReader
Le classi <xref:System.Data.DataTable> e <xref:System.Data.DataSet> dispongono di un metodo <xref:System.Data.DataTable.CreateDataReader%2A> che restituisce il contenuto del tipo <xref:System.Data.DataTable> o della raccolta <xref:System.Data.DataSet> dell'oggetto <xref:System.Data.DataSet.Tables%2A> come uno o più set di risultati forward-only di sola lettura.  
  
## <a name="example"></a>Esempio  
 Nell'applicazione console seguente viene creata un'istanza di <xref:System.Data.DataTable>. Nell'esempio viene quindi passata la <xref:System.Data.DataTable> compilazione a una routine che chiama <xref:System.Data.DataTable.CreateDataReader%2A> il metodo, che scorre <xref:System.Data.DataTableReader>i risultati contenuti all'interno di.  
  
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
- [DataTableReader](datatablereaders.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
