---
title: Definizione di chiavi primarie
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
ms.openlocfilehash: 159b23eb4ef5ca38ebce6e488080d315ec3be081
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151182"
---
# <a name="defining-primary-keys"></a>Definizione di chiavi primarie
In genere, in una tabella di database è presente una colonna o un gruppo di colonne che consente l'identificazione univoca di ogni riga della tabella. Tale colonna o gruppo di colonne di identificazione è definito chiave primaria.  
  
 Quando si identifica <xref:System.Data.DataColumn> un <xref:System.Data.DataTable.PrimaryKey%2A> singolo <xref:System.Data.DataTable>come oggetto per <xref:System.Data.DataColumn.AllowDBNull%2A> un oggetto , la <xref:System.Data.DataColumn.Unique%2A> tabella imposta automaticamente la proprietà della colonna su **false** e la proprietà su **true**. Per le chiavi primarie a più colonne, solo la proprietà **AllowDBNull** viene impostata automaticamente su **false**.  
  
 Il **PrimaryKey** proprietà <xref:System.Data.DataTable> di un riceve come valore una matrice di uno o più **DataColumn** oggetti, come illustrato negli esempi seguenti. Il primo esempio consente di definire una singola colonna come chiave primaria.  
  
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
- [Panoramica di ADO.NET](../ado-net-overview.md)
