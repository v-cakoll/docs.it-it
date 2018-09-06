---
title: Esplorazione di oggetti DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5e673f4-9b44-45ae-aaea-c504d1cc5d3e
ms.openlocfilehash: 1819d468d12c03ce0c4faac11f4b20b8fe0f9c33
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43805689"
---
# <a name="navigating-datarelations"></a>Esplorazione di oggetti DataRelation
Una delle funzioni principali di un oggetto <xref:System.Data.DataRelation> è di consentire la navigazione da una <xref:System.Data.DataTable> all'altra all'interno di un <xref:System.Data.DataSet>. In questo modo è possibile recuperare tutti i relativi <xref:System.Data.DataRow> oggetti in una **DataTable** quando viene fornito un singolo **DataRow** da un correlati **DataTable**. Ad esempio, dopo aver stabilito una **DataRelation** tra una tabella di clienti e una tabella di ordini, è possibile recuperare tutte le righe di ordine per un particolare cliente usando **GetChildRows**.  
  
 L'esempio di codice seguente crea una **DataRelation** tra il **clienti** tabella e il **ordini** tabella di un **set di dati** e restituisce tutti gli ordini per ogni cliente.  
  
 [!code-csharp[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/VB/source.vb#1)]  
  
 Nell'esempio successivo, basato su quello precedente, vengono correlate quattro tabelle e vengono esplorate tali relazioni. Come nell'esempio precedente, **CustomerID** si riferisce il **clienti** alla tabella il **ordini** tabella. Per ogni cliente nel **clienti** tabella, tutte le righe figlio nel **ordini** vengono determinate tabelle, per restituire il numero di ordini associati a un cliente specifico e i relativi **OrderID** i valori.  
  
 Nell'esempio espanso restituisce anche i valori di **OrderDetails** e **prodotti** tabelle. Il **ordini** tabella è correlata la **OrderDetails** tabella usando **OrderID** consente di determinare, per ogni ordine del cliente, quali prodotti e alle quantità ordinate. Poiché il **OrderDetails** tabella contiene solo le **ProductID** di un prodotto ordinato, **OrderDetails** è correlata a **prodotti** usando **ProductID** per restituire le **ProductName**. In questa relazione, il **prodotti** è la tabella padre e il **Order Details** è la tabella figlio. Di conseguenza, quando si scorrono le **OrderDetails** tabella **GetParentRow** viene chiamato per recuperare i relativi **ProductName** valore.  
  
 Si noti che durante la **DataRelation** viene creato per il **clienti** e **ordini** tabelle, viene specificato alcun valore per il **createConstraints**contrassegno (il valore predefinito è **true**). Si presuppone che tutte le righe il **ordini** tabella hanno un **CustomerID** valore presente nell'elemento padre **clienti** tabella. Se un **CustomerID** presente nella **ordini** tabella che non esiste nel **clienti** tabella, una <xref:System.Data.ForeignKeyConstraint> viene generata un'eccezione.  
  
 Quando la colonna figlio potrebbe contenere valori che non contiene la colonna padre, impostare il **createConstraints** flag **false** quando si aggiunge il **DataRelation**. Nell'esempio, il **createConstraints** flag è impostato su **false** per il **DataRelation** tra i **ordini** tabella e la  **OrderDetails** tabella. In questo modo l'applicazione restituire tutti i record il **OrderDetails** tabella e solo un subset dei record risultanti dalle **ordini** tabella senza generare un'eccezione in fase di esecuzione. Nell'esempio espanso viene generato un output con il seguente formato.  
  
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
  
 Esempio di codice seguente è un esempio espanso in cui i valori dal **OrderDetails** e **prodotti** vengono restituite le tabelle, solo un subset dei record del **ordini**restituita nella tabella.  
  
 [!code-csharp[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
