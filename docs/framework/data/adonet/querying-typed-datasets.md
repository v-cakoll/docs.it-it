---
title: Esecuzione di query su dataset tipizzati
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
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: bd78b4f47d7f48d7b4cbacdf53140758a05b7869
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="querying-typed-datasets"></a>Esecuzione di query su dataset tipizzati
Se si conosce lo schema di <xref:System.Data.DataSet> in fase di progettazione dell'applicazione, è consigliabile usare <xref:System.Data.DataSet> tipizzati con [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]. Un oggetto tipizzato <xref:System.Data.DataSet> è una classe che deriva da un <xref:System.Data.DataSet>. In quanto tale, tale oggetto eredita tutti i metodi, gli eventi e le proprietà di un <xref:System.Data.DataSet>. Inoltre, un oggetto tipizzato <xref:System.Data.DataSet> fornisce metodi fortemente tipizzati, proprietà ed eventi. È quindi possibile accedere a tabelle e colonne in base al nome, anziché usare metodi basati su raccolta. Le query risultano quindi più semplici e più leggibili. Per ulteriori informazioni, vedere [tipizzati](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]supporta inoltre l'esecuzione di query su un oggetto tipizzato <xref:System.Data.DataSet>. Con un oggetto tipizzato <xref:System.Data.DataSet>, non è necessario utilizzare il metodo generico <xref:System.Data.DataRowExtensions.Field%2A> metodo o <xref:System.Data.DataRowExtensions.SetField%2A> metodo per accedere ai dati di colonna.  I nomi delle proprietà sono disponibili in fase di compilazione perché le informazioni sul tipo è incluso nel <xref:System.Data.DataSet>. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]fornisce accesso ai valori di colonna come tipo corretto, in modo che gli errori di mancata corrispondenza di tipo vengono intercettati durante la compilazione del codice anziché in fase di esecuzione.  
  
 Prima di iniziare a eseguire query su un oggetto <xref:System.Data.DataSet> tipizzato, è necessario generare la classe usando Progettazione DataSet in [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  Per altre informazioni, vedere [Create and configure datasets](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio) (Creare e configurare set di dati).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata una query su un oggetto <xref:System.Data.DataSet> tipizzato.  
  
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
  
## <a name="see-also"></a>Vedere anche  
 [Esecuzione di query su set di dati](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 [Query tra tabelle](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 [Query su singola tabella](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)
