---
title: Creazione di un oggetto DataReader
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: b603e4fad628d0bb338213420059ffa411acd432
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="creating-a-datareader"></a>Creazione di un oggetto DataReader
Le classi <xref:System.Data.DataTable> e <xref:System.Data.DataSet> dispongono di un metodo <xref:System.Data.DataTable.CreateDataReader%2A> che restituisce il contenuto del tipo <xref:System.Data.DataTable> o della raccolta <xref:System.Data.DataSet> dell'oggetto <xref:System.Data.DataSet.Tables%2A> come uno o più set di risultati forward-only di sola lettura.  
  
## <a name="example"></a>Esempio  
 Nell'applicazione console seguente viene creata un'istanza di <xref:System.Data.DataTable>. Nell'esempio viene quindi passata la <xref:System.Data.DataTable> a una routine che chiama il <xref:System.Data.DataTable.CreateDataReader%2A> metodo, scorre i risultati contenuti all'interno di <xref:System.Data.DataTableReader>.  
  
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
 <xref:System.Data.DataTable.CreateDataReader%2A>  
 <xref:System.Data.DataSet.CreateDataReader%2A>  
 [DataTableReader](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
