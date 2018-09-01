---
title: Aggiunta di dati a un oggetto DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
ms.openlocfilehash: c1ebe2d735924c559f450f4041884dc9845e4fe0
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43396085"
---
# <a name="adding-data-to-a-datatable"></a><span data-ttu-id="fa1cc-102">Aggiunta di dati a un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="fa1cc-102">Adding Data to a DataTable</span></span>
<span data-ttu-id="fa1cc-103">Una volta creata una <xref:System.Data.DataTable> e definita la relativa struttura tramite colonne e vincoli, è possibile aggiungere nuove righe di dati alla tabella.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-103">After you create a <xref:System.Data.DataTable> and define its structure using columns and constraints, you can add new rows of data to the table.</span></span> <span data-ttu-id="fa1cc-104">Per aggiungere una nuova riga, dichiarare una nuova variabile come tipo <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-104">To add a new row, declare a new variable as type <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="fa1cc-105">Una nuova **DataRow** oggetto viene restituito quando si chiama il <xref:System.Data.DataTable.NewRow%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="fa1cc-105">A new **DataRow** object is returned when you call the <xref:System.Data.DataTable.NewRow%2A> method.</span></span> <span data-ttu-id="fa1cc-106">Il **DataTable** crea quindi il **DataRow** oggetto basati sulla struttura della tabella, come definito dal <xref:System.Data.DataColumnCollection>.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-106">The **DataTable** then creates the **DataRow** object based on the structure of the table, as defined by the <xref:System.Data.DataColumnCollection>.</span></span>  
  
 <span data-ttu-id="fa1cc-107">Nell'esempio seguente viene illustrato come creare una nuova riga chiamando la **NewRow** (metodo).</span><span class="sxs-lookup"><span data-stu-id="fa1cc-107">The following example demonstrates how to create a new row by calling the **NewRow** method.</span></span>  
  
```vb  
Dim workRow As DataRow = workTable.NewRow()  
```  
  
```csharp  
DataRow workRow = workTable.NewRow();  
```  
  
 <span data-ttu-id="fa1cc-108">È quindi possibile modificare la riga appena aggiunta usando un indice o il nome della colonna, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-108">You then can manipulate the newly added row using an index or the column name, as shown in the following example.</span></span>  
  
```vb  
workRow("CustLName") = "Smith"  
workRow(1) = "Smith"  
```  
  
```csharp  
workRow["CustLName"] = "Smith";  
workRow[1] = "Smith";  
```  
  
 <span data-ttu-id="fa1cc-109">Dopo che i dati vengono inseriti nella nuova riga, il **Add** metodo viene utilizzato per aggiungere la riga per il <xref:System.Data.DataRowCollection>, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-109">After data is inserted into the new row, the **Add** method is used to add the row to the <xref:System.Data.DataRowCollection>, shown in the following code.</span></span>  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 <span data-ttu-id="fa1cc-110">È inoltre possibile chiamare il **Add** per aggiungere una nuova riga passando una matrice di valori, tipizzata come <xref:System.Object>, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-110">You can also call the **Add** method to add a new row by passing in an array of values, typed as <xref:System.Object>, as shown in the following example.</span></span>  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 <span data-ttu-id="fa1cc-111">Passando una matrice di valori, tipizzata come **oggetti**, per il **Add** metodo crea una nuova riga all'interno della tabella e imposta i valori di colonna ai valori nella matrice di oggetti.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-111">Passing an array of values, typed as **Object**, to the **Add** method creates a new row inside the table and sets its column values to the values in the object array.</span></span> <span data-ttu-id="fa1cc-112">Notare che i valori contenuti nella matrice vengono associati in modo sequenziale alle colonne, in base all'ordine in cui sono presenti nella tabella.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-112">Note that values in the array are matched sequentially to the columns, based on the order in which they appear in the table.</span></span>  
  
 <span data-ttu-id="fa1cc-113">L'esempio seguente aggiunge 10 righe all'oggetto appena creato **clienti** tabella.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-113">The following example adds 10 rows to the newly created **Customers** table.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fa1cc-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa1cc-114">See Also</span></span>  
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataRowCollection>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="fa1cc-115">Manipolazione di dati in un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="fa1cc-115">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="fa1cc-116">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="fa1cc-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
