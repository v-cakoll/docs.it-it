---
title: Esplorazione di oggetti DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5e673f4-9b44-45ae-aaea-c504d1cc5d3e
ms.openlocfilehash: b7b1717317bb119538497f60bae48ec1da2286c8
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203329"
---
# <a name="navigating-datarelations"></a>Esplorazione di oggetti DataRelation
Una delle funzioni principali di un oggetto <xref:System.Data.DataRelation> è di consentire la navigazione da una <xref:System.Data.DataTable> all'altra all'interno di un <xref:System.Data.DataSet>. In questo modo è possibile recuperare tutti gli <xref:System.Data.DataRow> oggetti correlati in una **DataTable** quando viene specificato un singolo **DataRow** da un **DataTable**correlato. Ad esempio, dopo avere stabilito una DataRelation tra una tabella di clienti e una tabella di ordini, è possibile recuperare tutte le righe di ordine per una determinata riga del cliente utilizzando **GetChildRows**.  
  
 Nell'esempio di codice seguente viene creata una DataRelation tra la tabella **Customers** e la tabella **Orders** di un **DataSet** e vengono restituiti tutti gli ordini per ogni cliente.  
  
 [!code-csharp[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/VB/source.vb#1)]  
  
 Nell'esempio successivo, basato su quello precedente, vengono correlate quattro tabelle e vengono esplorate tali relazioni. Come nell'esempio precedente, **CustomerID** mette in correlazione la tabella Customers alla tabella Orders. Per ogni cliente nella tabella **Customers** vengono determinate tutte le righe figlio della tabella Orders, in modo da restituire il numero di ordini di un determinato cliente e i rispettivi valori **OrderID** .  
  
 Nell'esempio espanso vengono inoltre restituiti i valori delle tabelle **OrderDetails** e **Products** . La tabella Orders è correlata alla tabella **OrderDetails** con **OrderID** per determinare, per ogni ordine cliente, i prodotti e le quantità ordinati. Poiché la tabella **OrderDetails** contiene solo il **ProductID** di un prodotto ordinato, **OrderDetails** è correlato ai **prodotti** che utilizzano **ProductID** per restituire il **ProductName**. In questa relazione la tabella **Products** è l'elemento padre e la tabella **Order** Details è l'elemento figlio. Di conseguenza, quando si scorre la tabella **OrderDetails** , viene chiamato **GetParentRow** per recuperare il valore **ProductName** correlato.  
  
 Si noti che quando si crea DataRelation per le tabelle Customers e **Orders** , non viene specificato alcun valore per il flag **createConstraints** (il valore predefinito è **true**). Si presuppone che tutte le righe della tabella **Orders** dispongano di un valore **CustomerID** presente nella tabella **Customers** padre. Se nella tabella Orders esiste un **CustomerID** che non esiste nella tabella <xref:System.Data.ForeignKeyConstraint> Customers, viene generata un'eccezione.  
  
 Quando la colonna figlio potrebbe contenere valori non contenuti nella colonna padre, impostare il flag **createConstraints** su **false** quando si aggiunge la DataRelation. Nell'esempio, il flag **createConstraints** è impostato su **false** per l'oggetto **DataRelation** tra la tabella Orders e la tabella **OrderDetails** . Ciò consente all'applicazione di restituire tutti i record dalla tabella **OrderDetails** e solo un subset di record della tabella **Orders** senza generare un'eccezione in fase di esecuzione. Nell'esempio espanso viene generato un output con il seguente formato.  
  
```  
Customer ID: NORTS  
  Order ID: 10517  
        Order Date: 4/24/1997 12:00:00 AM  
           Product: Filo Mix  
          Quantity: 6  
           Product: Raclette Courdavault  
          Quantity: 4  
           Product: Outback Lager  
          Quantity: 6  
  Order ID: 11057  
        Order Date: 4/29/1998 12:00:00 AM  
           Product: Outback Lager  
          Quantity: 3  
```  
  
 L'esempio di codice seguente è un esempio espanso in cui vengono restituiti i valori delle tabelle **OrderDetails** e **Products** , con solo un subset dei record della tabella **Orders** da restituire.  
  
 [!code-csharp[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Oggetti DataSet, DataTable e DataView](index.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
