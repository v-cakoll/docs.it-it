---
title: Aggiunta di oggetti DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: 8157d296636d0f8661a35af35de561f5cc49c30b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784815"
---
# <a name="adding-datarelations"></a>Aggiunta di oggetti DataRelation
In un <xref:System.Data.DataSet> contenente più oggetti <xref:System.Data.DataTable> è possibile usare gli oggetti <xref:System.Data.DataRelation> per creare relazioni tra le tabelle, navigare tra di esse e restituire le righe padre o figlio da una tabella correlata.  
  
 Gli argomenti necessari per creare un oggetto **DataRelation** sono un nome per l'oggetto **DataRelation** creato e una matrice di uno o più <xref:System.Data.DataColumn> riferimenti alle colonne utilizzate come colonne padre e figlio nella relazione. Dopo aver creato un oggetto **DataRelation**, è possibile utilizzarlo per spostarsi tra le tabelle e recuperare i valori.  
  
 L'aggiunta di un oggetto **DataRelation** a un oggetto <xref:System.Data.DataSet> aggiunge, <xref:System.Data.UniqueConstraint> per impostazione predefinita, un oggetto <xref:System.Data.ForeignKeyConstraint> alla tabella padre e un oggetto alla tabella figlio. Per ulteriori informazioni su questi vincoli predefiniti, vedere [vincoli DataTable](datatable-constraints.md).  
  
 Nell'esempio di codice seguente viene creato un oggetto **DataRelation** utilizzando <xref:System.Data.DataTable> due <xref:System.Data.DataSet>oggetti in un oggetto. Ogni <xref:System.Data.DataTable> contiene una colonna denominata **CustID**, che funge da collegamento tra i due <xref:System.Data.DataTable> oggetti. Nell'esempio viene aggiunto un singolo oggetto **DataRelation** alla raccolta **Relations** dell'oggetto <xref:System.Data.DataSet>. Il primo argomento nell'esempio specifica il nome dell'oggetto **DataRelation** da creare. Il secondo argomento imposta la **DataColumn** padre e il terzo argomento imposta la **DataColumn**figlio.  
  
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
  
 Un oggetto **DataRelation** dispone inoltre di una proprietà **annidata** che, se impostata su **true**, determina l'annidamento delle righe della tabella figlio all'interno della riga associata della tabella padre quando vengono scritti come <xref:System.Data.DataSet.WriteXml%2A> elementi XML mediante. Per altre informazioni, vedere [Uso di XML in un set di dati](using-xml-in-a-dataset.md).  
  
## <a name="see-also"></a>Vedere anche

- [Oggetti DataSet, DataTable e DataView](index.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
