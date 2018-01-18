---
title: Definizione di chiavi primarie
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
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: abd1dc4b515121343b2ca9674b263c327d153fad
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="defining-primary-keys"></a>Definizione di chiavi primarie
In genere, in una tabella di database è presente una colonna o un gruppo di colonne che consente l'identificazione univoca di ogni riga della tabella. Tale colonna o gruppo di colonne di identificazione è definito chiave primaria.  
  
 Quando si identifica un singolo <xref:System.Data.DataColumn> come il <xref:System.Data.DataTable.PrimaryKey%2A> per un <xref:System.Data.DataTable>, imposta automaticamente la tabella di <xref:System.Data.DataColumn.AllowDBNull%2A> proprietà della colonna **false** e <xref:System.Data.DataColumn.Unique%2A> proprietà  **true**. Per più colonne chiavi primarie, solo il **AllowDBNull** proprietà viene impostata automaticamente su **false**.  
  
 Il **PrimaryKey** proprietà di un <xref:System.Data.DataTable> riceve come valore una matrice di uno o più **DataColumn** oggetti, come illustrato negli esempi seguenti. Il primo esempio consente di definire una singola colonna come chiave primaria.  
  
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
 <xref:System.Data.DataTable>  
 [Definizione dello schema DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
