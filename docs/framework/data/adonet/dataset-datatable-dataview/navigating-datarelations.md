---
title: Esplorazione di oggetti DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5e673f4-9b44-45ae-aaea-c504d1cc5d3e
ms.openlocfilehash: c46007fb86a76405fd99d6e943779238d6885aa8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761428"
---
# <a name="navigating-datarelations"></a>Esplorazione di oggetti DataRelation
Una delle funzioni principali di un oggetto <xref:System.Data.DataRelation> è di consentire la navigazione da una <xref:System.Data.DataTable> all'altra all'interno di un <xref:System.Data.DataSet>. In questo modo è possibile recuperare tutti gli <xref:System.Data.DataRow> gli oggetti in uno **DataTable** quando viene specificato un singolo **DataRow** da un processo di **DataTable**. Ad esempio, dopo aver stabilito un **DataRelation** tra una tabella di clienti e una tabella di ordini, è possibile recuperare tutte le righe di ordine per un particolare cliente usando **GetChildRows**.  
  
 L'esempio di codice seguente crea un **DataRelation** tra il **clienti** tabella e **ordini** tabella di un **DataSet** e restituisce tutti gli ordini per ogni cliente.  
  
 [!code-csharp[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/VB/source.vb#1)]  
  
 Nell'esempio successivo, basato su quello precedente, vengono correlate quattro tabelle e vengono esplorate tali relazioni. Come nell'esempio precedente, **CustomerID** si riferisce il **clienti** tabella il **ordini** tabella. Per ogni cliente nel **clienti** tabella, tutte le righe figlio il **ordini** tabella dipendono, per restituire il numero di ordini di un determinato cliente e le relative **OrderID** valori.  
  
 Nell'esempio espanso restituisce anche i valori di **OrderDetails** e **prodotti** tabelle. Il **ordini** tabella è correlata al **OrderDetails** tramite **OrderID** per determinare per ogni ordine del cliente, quali prodotti e le quantità ordinate. Poiché il **OrderDetails** tabella contiene solo il **ProductID** di un prodotto ordinato, **OrderDetails** è correlata a **prodotti** utilizzando **ProductID** per restituire il **ProductName**. In questo tipo di relazione di **prodotti** è la tabella padre e **Order Details** è la tabella figlio. Di conseguenza, quando si scorre il **OrderDetails** tabella **GetParentRow** viene chiamata per recuperare l'oggetto correlato **ProductName** valore.  
  
 Si noti che quando il **DataRelation** viene creato per il **clienti** e **ordini** tabelle, viene specificato alcun valore per il **createConstraints**flag (il valore predefinito è **true**). Si presuppone che tutte le righe il **ordini** tabella hanno un **CustomerID** valore esistente nell'elemento padre **clienti** tabella. Se un **CustomerID** esiste nel **ordini** tabella che non esiste nel **clienti** tabella, una <xref:System.Data.ForeignKeyConstraint> viene generata un'eccezione.  
  
 Quando la colonna figlio può contenere valori che non contiene la colonna padre, impostare il **createConstraints** flag **false** quando si aggiunge il **DataRelation**. Nell'esempio di **createConstraints** flag è impostato su **false** per il **DataRelation** tra il **ordini** tabella e il  **OrderDetails** tabella. Questo consente all'applicazione restituire tutti i record di **OrderDetails** tabella e solo un subset di record dal **ordini** tabella senza generare un'eccezione in fase di esecuzione. Nell'esempio espanso viene generato un output con il seguente formato.  
  
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
  
 L'esempio di codice seguente è un esempio ampliato in cui i valori di **OrderDetails** e **prodotti** vengono restituite le tabelle, solo un subset dei record del **ordini**tabella restituita.  
  
 [!code-csharp[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
