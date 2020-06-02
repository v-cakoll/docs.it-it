---
title: Aggiunta di dati a un oggetto DataTable
description: Fare riferimento a questo codice di esempio per aggiungere nuove righe di dati a una tabella in ADO.NET, dopo avere creato una DataTable e definirne la struttura usando le colonne e i vincoli.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
ms.openlocfilehash: 94ebc97d5f90b5bb92186ba6f33015633bd01127
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286934"
---
# <a name="adding-data-to-a-datatable"></a><span data-ttu-id="b268d-103">Aggiunta di dati a un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="b268d-103">Adding Data to a DataTable</span></span>
<span data-ttu-id="b268d-104">Una volta creata una <xref:System.Data.DataTable> e definita la relativa struttura tramite colonne e vincoli, è possibile aggiungere nuove righe di dati alla tabella.</span><span class="sxs-lookup"><span data-stu-id="b268d-104">After you create a <xref:System.Data.DataTable> and define its structure using columns and constraints, you can add new rows of data to the table.</span></span> <span data-ttu-id="b268d-105">Per aggiungere una nuova riga, dichiarare una nuova variabile come tipo <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="b268d-105">To add a new row, declare a new variable as type <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="b268d-106">Quando si chiama il metodo, viene restituito un nuovo oggetto **DataRow** <xref:System.Data.DataTable.NewRow%2A> .</span><span class="sxs-lookup"><span data-stu-id="b268d-106">A new **DataRow** object is returned when you call the <xref:System.Data.DataTable.NewRow%2A> method.</span></span> <span data-ttu-id="b268d-107">Il **DataTable** crea quindi l'oggetto **DataRow** in base alla struttura della tabella, come definito da <xref:System.Data.DataColumnCollection> .</span><span class="sxs-lookup"><span data-stu-id="b268d-107">The **DataTable** then creates the **DataRow** object based on the structure of the table, as defined by the <xref:System.Data.DataColumnCollection>.</span></span>  
  
 <span data-ttu-id="b268d-108">Nell'esempio seguente viene illustrato come creare una nuova riga chiamando il metodo **NewRow** .</span><span class="sxs-lookup"><span data-stu-id="b268d-108">The following example demonstrates how to create a new row by calling the **NewRow** method.</span></span>  
  
```vb  
Dim workRow As DataRow = workTable.NewRow()  
```  
  
```csharp  
DataRow workRow = workTable.NewRow();  
```  
  
 <span data-ttu-id="b268d-109">È quindi possibile modificare la riga appena aggiunta usando un indice o il nome della colonna, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b268d-109">You then can manipulate the newly added row using an index or the column name, as shown in the following example.</span></span>  
  
```vb  
workRow("CustLName") = "Smith"  
workRow(1) = "Smith"  
```  
  
```csharp  
workRow["CustLName"] = "Smith";  
workRow[1] = "Smith";  
```  
  
 <span data-ttu-id="b268d-110">Dopo l'inserimento dei dati nella nuova riga, il metodo **Add** viene utilizzato per aggiungere la riga a <xref:System.Data.DataRowCollection> , illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b268d-110">After data is inserted into the new row, the **Add** method is used to add the row to the <xref:System.Data.DataRowCollection>, shown in the following code.</span></span>  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 <span data-ttu-id="b268d-111">È anche possibile chiamare il metodo **Add** per aggiungere una nuova riga passando una matrice di valori, tipizzata come <xref:System.Object> , come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b268d-111">You can also call the **Add** method to add a new row by passing in an array of values, typed as <xref:System.Object>, as shown in the following example.</span></span>  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 <span data-ttu-id="b268d-112">Il passaggio di una matrice di valori, tipizzato come **oggetto**, al metodo **Add** crea una nuova riga all'interno della tabella e imposta i relativi valori di colonna sui valori nella matrice di oggetti.</span><span class="sxs-lookup"><span data-stu-id="b268d-112">Passing an array of values, typed as **Object**, to the **Add** method creates a new row inside the table and sets its column values to the values in the object array.</span></span> <span data-ttu-id="b268d-113">Notare che i valori contenuti nella matrice vengono associati in modo sequenziale alle colonne, in base all'ordine in cui sono presenti nella tabella.</span><span class="sxs-lookup"><span data-stu-id="b268d-113">Note that values in the array are matched sequentially to the columns, based on the order in which they appear in the table.</span></span>  
  
 <span data-ttu-id="b268d-114">Nell'esempio seguente vengono aggiunte 10 righe alla tabella **Customers** appena creata.</span><span class="sxs-lookup"><span data-stu-id="b268d-114">The following example adds 10 rows to the newly created **Customers** table.</span></span>  
  
```vb  
Dim workRow As DataRow  
Dim i As Integer  
  
For i = 0 To 9  
  workRow = workTable.NewRow()  
  workRow(0) = i  
  workRow(1) = "CustName" & I.ToString()  
  workTable.Rows.Add(workRow)  
Next  
```  
  
```csharp  
DataRow workRow;  
  
for (int i = 0; i <= 9; i++)
{  
  workRow = workTable.NewRow();  
  workRow[0] = i;  
  workRow[1] = "CustName" + i.ToString();  
  workTable.Rows.Add(workRow);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b268d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b268d-115">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="b268d-116">Manipolazione di dati in un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="b268d-116">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="b268d-117">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b268d-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
