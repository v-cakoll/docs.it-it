---
title: Definizione di chiavi primarie
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
ms.openlocfilehash: dbfd8a8b207c0da9403ac1f8ab36557c4abe383b
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204916"
---
# <a name="defining-primary-keys"></a>Definizione di chiavi primarie
In genere, in una tabella di database è presente una colonna o un gruppo di colonne che consente l'identificazione univoca di ogni riga della tabella. Tale colonna o gruppo di colonne di identificazione è definito chiave primaria.  
  
 Quando si identifica un singolo <xref:System.Data.DataColumn> <xref:System.Data.DataTable.PrimaryKey%2A> come per un oggetto <xref:System.Data.DataTable>, la tabella imposta automaticamente la <xref:System.Data.DataColumn.AllowDBNull%2A> proprietà della colonna su **false** e la <xref:System.Data.DataColumn.Unique%2A> proprietà su **true**. Per le chiavi primarie a più colonne, solo la proprietà **AllowDBNull** viene impostata automaticamente su **false**.  
  
 La proprietà **PrimaryKey** di un <xref:System.Data.DataTable> oggetto riceve come valore una matrice di uno o più oggetti **DataColumn** , come illustrato negli esempi seguenti. Il primo esempio consente di definire una singola colonna come chiave primaria.  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustID")}  
  
' Or  
  
Dim columns(1) As DataColumn  
columns(0) = workTable.Columns("CustID")  
workTable.PrimaryKey = columns  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustID"]};  
  
// Or  
  
DataColumn[] columns = new DataColumn[1];  
columns[0] = workTable.Columns["CustID"];  
workTable.PrimaryKey = columns;  
```  
  
 L'esempio seguente consente di definire due colonne come chiave primaria.  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustLName"), _  
                                         workTable.Columns("CustFName")}  
  
' Or  
  
Dim keyColumn(2) As DataColumn  
keyColumn(0) = workTable.Columns("CustLName")  
keyColumn(1) = workTable.Columns("CustFName")  
workTable.PrimaryKey = keyColumn  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustLName"],   
                                         workTable.Columns["CustFName"]};  
  
// Or  
  
DataColumn[] keyColumn = new DataColumn[2];  
keyColumn[0] = workTable.Columns["CustLName"];  
keyColumn[1] = workTable.Columns["CustFName"];  
workTable.PrimaryKey = keyColumn;  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Data.DataTable>
- [Definizione dello schema DataTable](datatable-schema-definition.md)
- [DataTable](datatables.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
