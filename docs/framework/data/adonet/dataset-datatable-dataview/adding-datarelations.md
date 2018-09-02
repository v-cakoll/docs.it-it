---
title: Aggiunta di oggetti DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: d0f481979ead7af775d462a2624ec43080e2c5a9
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43399194"
---
# <a name="adding-datarelations"></a>Aggiunta di oggetti DataRelation
In un <xref:System.Data.DataSet> contenente più oggetti <xref:System.Data.DataTable> è possibile usare gli oggetti <xref:System.Data.DataRelation> per creare relazioni tra le tabelle, navigare tra di esse e restituire le righe padre o figlio da una tabella correlata.  
  
 Gli argomenti richiesti per creare un **DataRelation** sono un nome per il **DataRelation** viene creato e una matrice di uno o più <xref:System.Data.DataColumn> riferimenti alle colonne che fungono da padre e figlio colonne coinvolte nella relazione. Dopo aver creato un **DataRelation**, è possibile usare per navigare tra le tabelle e recuperare i valori.  
  
 Aggiunta di un **DataRelation** a un <xref:System.Data.DataSet> aggiunge, per impostazione predefinita, una <xref:System.Data.UniqueConstraint> alla tabella padre e un <xref:System.Data.ForeignKeyConstraint> alla tabella figlio. Per altre informazioni su questi vincoli predefiniti, vedere [vincoli DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 L'esempio di codice seguente crea una **DataRelation** usando due <xref:System.Data.DataTable> gli oggetti in un <xref:System.Data.DataSet>. Ciascuna <xref:System.Data.DataTable> contiene una colonna denominata **CustID**, che agisce come un collegamento tra i due <xref:System.Data.DataTable> oggetti. Nell'esempio viene aggiunto un unico **DataRelation** per il **relazioni** raccolta del <xref:System.Data.DataSet>. Nell'esempio il primo argomento specifica il nome del **DataRelation** creato. Il secondo argomento imposta l'elemento padre **DataColumn** e il terzo argomento imposta l'elemento figlio **DataColumn**.  
  
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
  
 Oggetto **DataRelation** dispone anche di un **Nested** proprietà che, quando impostato su **true**, fa in modo che le righe dalla tabella figlio all'interno della riga associata nella tabella padre scrittura come elementi XML utilizzando <xref:System.Data.DataSet.WriteXml%2A> . Per altre informazioni, vedere [Uso di XML in un set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
