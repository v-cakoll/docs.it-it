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
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: dffced0e3d8cd28699d41ea6bb286e3d59f16bb2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="defining-primary-keys"></a><span data-ttu-id="eaaa6-102">Definizione di chiavi primarie</span><span class="sxs-lookup"><span data-stu-id="eaaa6-102">Defining Primary Keys</span></span>
<span data-ttu-id="eaaa6-103">In genere, in una tabella di database è presente una colonna o un gruppo di colonne che consente l'identificazione univoca di ogni riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="eaaa6-103">A database table commonly has a column or group of columns that uniquely identifies each row in the table.</span></span> <span data-ttu-id="eaaa6-104">Tale colonna o gruppo di colonne di identificazione è definito chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="eaaa6-104">This identifying column or group of columns is called the primary key.</span></span>  
  
 <span data-ttu-id="eaaa6-105">Quando si identifica un singolo <xref:System.Data.DataColumn> come il <xref:System.Data.DataTable.PrimaryKey%2A> per un <xref:System.Data.DataTable>, imposta automaticamente la tabella di <xref:System.Data.DataColumn.AllowDBNull%2A> proprietà della colonna **false** e <xref:System.Data.DataColumn.Unique%2A> proprietà  **true**.</span><span class="sxs-lookup"><span data-stu-id="eaaa6-105">When you identify a single <xref:System.Data.DataColumn> as the <xref:System.Data.DataTable.PrimaryKey%2A> for a <xref:System.Data.DataTable>, the table automatically sets the <xref:System.Data.DataColumn.AllowDBNull%2A> property of the column to **false** and the <xref:System.Data.DataColumn.Unique%2A> property to **true**.</span></span> <span data-ttu-id="eaaa6-106">Per più colonne chiavi primarie, solo il **AllowDBNull** proprietà viene impostata automaticamente su **false**.</span><span class="sxs-lookup"><span data-stu-id="eaaa6-106">For multiple-column primary keys, only the **AllowDBNull** property is automatically set to **false**.</span></span>  
  
 <span data-ttu-id="eaaa6-107">Il **PrimaryKey** proprietà di un <xref:System.Data.DataTable> riceve come valore una matrice di uno o più **DataColumn** oggetti, come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="eaaa6-107">The **PrimaryKey** property of a <xref:System.Data.DataTable> receives as its value an array of one or more **DataColumn** objects, as shown in the following examples.</span></span> <span data-ttu-id="eaaa6-108">Il primo esempio consente di definire una singola colonna come chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="eaaa6-108">The first example defines a single column as the primary key.</span></span>  
  
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
  
 <span data-ttu-id="eaaa6-109">L'esempio seguente consente di definire due colonne come chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="eaaa6-109">The following example defines two columns as a primary key.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="eaaa6-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eaaa6-110">See Also</span></span>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="eaaa6-111">Definizione dello schema DataTable</span><span class="sxs-lookup"><span data-stu-id="eaaa6-111">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [<span data-ttu-id="eaaa6-112">DataTable</span><span class="sxs-lookup"><span data-stu-id="eaaa6-112">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="eaaa6-113">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="eaaa6-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
