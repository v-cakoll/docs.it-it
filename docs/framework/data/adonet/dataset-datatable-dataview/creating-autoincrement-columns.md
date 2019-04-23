---
title: Creazione di colonne AutoIncrement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 99c52b93cee858511d50aba2f30f2b9f96d91ccd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090940"
---
# <a name="creating-autoincrement-columns"></a><span data-ttu-id="5ff10-102">Creazione di colonne AutoIncrement</span><span class="sxs-lookup"><span data-stu-id="5ff10-102">Creating AutoIncrement Columns</span></span>
<span data-ttu-id="5ff10-103">Per assicurarsi che i valori contenuti in una colonna siano univoci, è possibile impostare l'incremento automatico dei valori di colonna a ogni aggiunta di nuove colonne alla tabella.</span><span class="sxs-lookup"><span data-stu-id="5ff10-103">To ensure unique column values, you can set the column values to increment automatically when new rows are added to the table.</span></span> <span data-ttu-id="5ff10-104">Per creare un incremento automatico <xref:System.Data.DataColumn>, impostare il <xref:System.Data.DataColumn.AutoIncrement%2A> proprietà della colonna **true**.</span><span class="sxs-lookup"><span data-stu-id="5ff10-104">To create an auto-incrementing <xref:System.Data.DataColumn>, set the <xref:System.Data.DataColumn.AutoIncrement%2A> property of the column to **true**.</span></span> <span data-ttu-id="5ff10-105">Il <xref:System.Data.DataColumn> quindi inizia con il valore definito nel <xref:System.Data.DataColumn.AutoIncrementSeed%2A> proprietà e con ogni riga aggiunta del valore del **AutoIncrement** aumenta il valore definito nella colonna di <xref:System.Data.DataColumn.AutoIncrementStep%2A> proprietà della colonna.</span><span class="sxs-lookup"><span data-stu-id="5ff10-105">The <xref:System.Data.DataColumn> then starts with the value defined in the <xref:System.Data.DataColumn.AutoIncrementSeed%2A> property, and with each row added the value of the **AutoIncrement** column increases by the value defined in the <xref:System.Data.DataColumn.AutoIncrementStep%2A> property of the column.</span></span>  
  
 <span data-ttu-id="5ff10-106">Per **AutoIncrement** colonne, è consigliabile che le <xref:System.Data.DataColumn.ReadOnly%2A> proprietà del **DataColumn** essere impostato su **true**.</span><span class="sxs-lookup"><span data-stu-id="5ff10-106">For **AutoIncrement** columns, we recommend that the <xref:System.Data.DataColumn.ReadOnly%2A> property of the **DataColumn** be set to **true**.</span></span>  
  
 <span data-ttu-id="5ff10-107">Nell'esempio seguente viene illustrato come creare una colonna con valore iniziale pari a 200 e con incrementi in 3 passaggi.</span><span class="sxs-lookup"><span data-stu-id="5ff10-107">The following example demonstrates how to create a column that starts with a value of 200 and adds incrementally in steps of 3.</span></span>  
  
```vb  
Dim workColumn As DataColumn = workTable.Columns.Add( _  
    "CustomerID", typeof(Int32))  
workColumn.AutoIncrement = true  
workColumn.AutoIncrementSeed = 200  
workColumn.AutoIncrementStep = 3  
```  
  
```csharp  
DataColumn workColumn = workTable.Columns.Add(  
    "CustomerID", typeof(Int32));  
workColumn.AutoIncrement = true;  
workColumn.AutoIncrementSeed = 200;  
workColumn.AutoIncrementStep = 3;  
```  
  
## <a name="see-also"></a><span data-ttu-id="5ff10-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ff10-108">See also</span></span>

- <xref:System.Data.DataColumn>
- [<span data-ttu-id="5ff10-109">Definizione dello schema DataTable</span><span class="sxs-lookup"><span data-stu-id="5ff10-109">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)
- [<span data-ttu-id="5ff10-110">DataTable</span><span class="sxs-lookup"><span data-stu-id="5ff10-110">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [<span data-ttu-id="5ff10-111">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="5ff10-111">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
