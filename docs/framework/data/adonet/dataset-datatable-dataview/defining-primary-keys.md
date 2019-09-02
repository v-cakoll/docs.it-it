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
# <a name="defining-primary-keys"></a><span data-ttu-id="dae43-102">Definizione di chiavi primarie</span><span class="sxs-lookup"><span data-stu-id="dae43-102">Defining Primary Keys</span></span>
<span data-ttu-id="dae43-103">In genere, in una tabella di database è presente una colonna o un gruppo di colonne che consente l'identificazione univoca di ogni riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="dae43-103">A database table commonly has a column or group of columns that uniquely identifies each row in the table.</span></span> <span data-ttu-id="dae43-104">Tale colonna o gruppo di colonne di identificazione è definito chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="dae43-104">This identifying column or group of columns is called the primary key.</span></span>  
  
 <span data-ttu-id="dae43-105">Quando si identifica un singolo <xref:System.Data.DataColumn> <xref:System.Data.DataTable.PrimaryKey%2A> come per un oggetto <xref:System.Data.DataTable>, la tabella imposta automaticamente la <xref:System.Data.DataColumn.AllowDBNull%2A> proprietà della colonna su **false** e la <xref:System.Data.DataColumn.Unique%2A> proprietà su **true**.</span><span class="sxs-lookup"><span data-stu-id="dae43-105">When you identify a single <xref:System.Data.DataColumn> as the <xref:System.Data.DataTable.PrimaryKey%2A> for a <xref:System.Data.DataTable>, the table automatically sets the <xref:System.Data.DataColumn.AllowDBNull%2A> property of the column to **false** and the <xref:System.Data.DataColumn.Unique%2A> property to **true**.</span></span> <span data-ttu-id="dae43-106">Per le chiavi primarie a più colonne, solo la proprietà **AllowDBNull** viene impostata automaticamente su **false**.</span><span class="sxs-lookup"><span data-stu-id="dae43-106">For multiple-column primary keys, only the **AllowDBNull** property is automatically set to **false**.</span></span>  
  
 <span data-ttu-id="dae43-107">La proprietà **PrimaryKey** di un <xref:System.Data.DataTable> oggetto riceve come valore una matrice di uno o più oggetti **DataColumn** , come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="dae43-107">The **PrimaryKey** property of a <xref:System.Data.DataTable> receives as its value an array of one or more **DataColumn** objects, as shown in the following examples.</span></span> <span data-ttu-id="dae43-108">Il primo esempio consente di definire una singola colonna come chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="dae43-108">The first example defines a single column as the primary key.</span></span>  
  
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
  
 <span data-ttu-id="dae43-109">L'esempio seguente consente di definire due colonne come chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="dae43-109">The following example defines two columns as a primary key.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dae43-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dae43-110">See also</span></span>

- <xref:System.Data.DataTable>
- [<span data-ttu-id="dae43-111">Definizione dello schema DataTable</span><span class="sxs-lookup"><span data-stu-id="dae43-111">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="dae43-112">DataTable</span><span class="sxs-lookup"><span data-stu-id="dae43-112">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="dae43-113">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="dae43-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
