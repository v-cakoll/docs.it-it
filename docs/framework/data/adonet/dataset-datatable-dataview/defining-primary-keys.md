---
title: Definizione di chiavi primarie
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
ms.openlocfilehash: 0f87b1b730eecf0edad75bd87ca8b491b96e1d2b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784713"
---
# <a name="defining-primary-keys"></a><span data-ttu-id="9afd2-102">Definizione di chiavi primarie</span><span class="sxs-lookup"><span data-stu-id="9afd2-102">Defining Primary Keys</span></span>
<span data-ttu-id="9afd2-103">In genere, in una tabella di database è presente una colonna o un gruppo di colonne che consente l'identificazione univoca di ogni riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="9afd2-103">A database table commonly has a column or group of columns that uniquely identifies each row in the table.</span></span> <span data-ttu-id="9afd2-104">Tale colonna o gruppo di colonne di identificazione è definito chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="9afd2-104">This identifying column or group of columns is called the primary key.</span></span>  
  
 <span data-ttu-id="9afd2-105">Quando si identifica un singolo <xref:System.Data.DataColumn> <xref:System.Data.DataTable.PrimaryKey%2A> come per un oggetto <xref:System.Data.DataTable>, la tabella imposta automaticamente la <xref:System.Data.DataColumn.AllowDBNull%2A> proprietà della colonna su **false** e la <xref:System.Data.DataColumn.Unique%2A> proprietà su **true**.</span><span class="sxs-lookup"><span data-stu-id="9afd2-105">When you identify a single <xref:System.Data.DataColumn> as the <xref:System.Data.DataTable.PrimaryKey%2A> for a <xref:System.Data.DataTable>, the table automatically sets the <xref:System.Data.DataColumn.AllowDBNull%2A> property of the column to **false** and the <xref:System.Data.DataColumn.Unique%2A> property to **true**.</span></span> <span data-ttu-id="9afd2-106">Per le chiavi primarie a più colonne, solo la proprietà **AllowDBNull** viene impostata automaticamente su **false**.</span><span class="sxs-lookup"><span data-stu-id="9afd2-106">For multiple-column primary keys, only the **AllowDBNull** property is automatically set to **false**.</span></span>  
  
 <span data-ttu-id="9afd2-107">La proprietà **PrimaryKey** di un <xref:System.Data.DataTable> oggetto riceve come valore una matrice di uno o più oggetti **DataColumn** , come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="9afd2-107">The **PrimaryKey** property of a <xref:System.Data.DataTable> receives as its value an array of one or more **DataColumn** objects, as shown in the following examples.</span></span> <span data-ttu-id="9afd2-108">Il primo esempio consente di definire una singola colonna come chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="9afd2-108">The first example defines a single column as the primary key.</span></span>  
  
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
  
 <span data-ttu-id="9afd2-109">L'esempio seguente consente di definire due colonne come chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="9afd2-109">The following example defines two columns as a primary key.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9afd2-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9afd2-110">See also</span></span>

- <xref:System.Data.DataTable>
- [<span data-ttu-id="9afd2-111">Definizione dello schema DataTable</span><span class="sxs-lookup"><span data-stu-id="9afd2-111">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="9afd2-112">DataTable</span><span class="sxs-lookup"><span data-stu-id="9afd2-112">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="9afd2-113">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9afd2-113">ADO.NET Overview</span></span>](../ado-net-overview.md)
