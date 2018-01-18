---
title: Aggiunta di oggetti DataRelation
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
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 4650ccc5324489fb5c577cf2542ae95e1904441a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="adding-datarelations"></a>Aggiunta di oggetti DataRelation
In un <xref:System.Data.DataSet> contenente più oggetti <xref:System.Data.DataTable> è possibile usare gli oggetti <xref:System.Data.DataRelation> per creare relazioni tra le tabelle, navigare tra di esse e restituire le righe padre o figlio da una tabella correlata.  
  
 Gli argomenti necessari per creare un **DataRelation** sono un nome per il **DataRelation** creato e una matrice di uno o più <xref:System.Data.DataColumn> i riferimenti alle colonne che fungono da padre e figlio colonne nella relazione. Dopo aver creato un **DataRelation**, è possibile utilizzare per navigare tra le tabelle e recuperare i valori.  
  
 Aggiunta di un **DataRelation** per un <xref:System.Data.DataSet> aggiunge, per impostazione predefinita, un <xref:System.Data.UniqueConstraint> alla tabella padre e un <xref:System.Data.ForeignKeyConstraint> alla tabella figlio. Per ulteriori informazioni sui vincoli predefiniti, vedere [vincoli DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 L'esempio di codice seguente crea un **DataRelation** utilizzando due <xref:System.Data.DataTable> gli oggetti in un <xref:System.Data.DataSet>. Ogni <xref:System.Data.DataTable> contiene una colonna denominata **CustID**, che funge da collegamento tra i due <xref:System.Data.DataTable> oggetti. Nell'esempio viene aggiunto un singolo **DataRelation** per il **relazioni** insieme il <xref:System.Data.DataSet>. Il primo argomento dell'esempio specifica il nome del **DataRelation** da creare. Il secondo argomento imposta l'elemento padre **DataColumn** e il terzo argomento imposta l'elemento figlio **DataColumn**.  
  
```vb  
customerOrders.Relations.Add("CustOrders", _  
  customerOrders.Tables("Customers").Columns("CustID"), _  
  customerOrders.Tables("Orders").Columns("CustID"))  
```  
  
```csharp  
customerOrders.Relations.Add("CustOrders",  
  customerOrders.Tables["Customers"].Columns["CustID"],  
  customerOrders.Tables["Orders"].Columns["CustID"]);  
```  
  
 A **DataRelation** dispone anche di un **Nested** proprietà che, se impostato su **true**, fa sì che le righe della tabella figlio all'interno della riga associata nella tabella padre Quando scritte come elementi XML tramite <xref:System.Data.DataSet.WriteXml%2A> . Per altre informazioni, vedere [Uso di XML in un set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
