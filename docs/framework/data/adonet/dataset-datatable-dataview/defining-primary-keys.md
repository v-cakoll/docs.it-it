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
# <a name="defining-primary-keys"></a><span data-ttu-id="ba6f2-102">Definizione di chiavi primarie</span><span class="sxs-lookup"><span data-stu-id="ba6f2-102">Defining Primary Keys</span></span>
<span data-ttu-id="ba6f2-103">In genere, in una tabella di database è presente una colonna o un gruppo di colonne che consente l'identificazione univoca di ogni riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="ba6f2-103">A database table commonly has a column or group of columns that uniquely identifies each row in the table.</span></span> <span data-ttu-id="ba6f2-104">Tale colonna o gruppo di colonne di identificazione è definito chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="ba6f2-104">This identifying column or group of columns is called the primary key.</span></span>  
  
 <span data-ttu-id="ba6f2-105">Quando si identifica <xref:System.Data.DataColumn> un <xref:System.Data.DataTable.PrimaryKey%2A> singolo <xref:System.Data.DataTable>come oggetto per <xref:System.Data.DataColumn.AllowDBNull%2A> un oggetto , la <xref:System.Data.DataColumn.Unique%2A> tabella imposta automaticamente la proprietà della colonna su **false** e la proprietà su **true**.</span><span class="sxs-lookup"><span data-stu-id="ba6f2-105">When you identify a single <xref:System.Data.DataColumn> as the <xref:System.Data.DataTable.PrimaryKey%2A> for a <xref:System.Data.DataTable>, the table automatically sets the <xref:System.Data.DataColumn.AllowDBNull%2A> property of the column to **false** and the <xref:System.Data.DataColumn.Unique%2A> property to **true**.</span></span> <span data-ttu-id="ba6f2-106">Per le chiavi primarie a più colonne, solo la proprietà **AllowDBNull** viene impostata automaticamente su **false**.</span><span class="sxs-lookup"><span data-stu-id="ba6f2-106">For multiple-column primary keys, only the **AllowDBNull** property is automatically set to **false**.</span></span>  
  
 <span data-ttu-id="ba6f2-107">Il **PrimaryKey** proprietà <xref:System.Data.DataTable> di un riceve come valore una matrice di uno o più **DataColumn** oggetti, come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="ba6f2-107">The **PrimaryKey** property of a <xref:System.Data.DataTable> receives as its value an array of one or more **DataColumn** objects, as shown in the following examples.</span></span> <span data-ttu-id="ba6f2-108">Il primo esempio consente di definire una singola colonna come chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="ba6f2-108">The first example defines a single column as the primary key.</span></span>  
  
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
  
 <span data-ttu-id="ba6f2-109">L'esempio seguente consente di definire due colonne come chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="ba6f2-109">The following example defines two columns as a primary key.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ba6f2-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba6f2-110">See also</span></span>

- <xref:System.Data.DataTable>
- [<span data-ttu-id="ba6f2-111">Definizione dello schema DataTable</span><span class="sxs-lookup"><span data-stu-id="ba6f2-111">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="ba6f2-112">DataTable</span><span class="sxs-lookup"><span data-stu-id="ba6f2-112">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="ba6f2-113">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ba6f2-113">ADO.NET Overview</span></span>](../ado-net-overview.md)
