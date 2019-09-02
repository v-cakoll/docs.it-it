---
title: Creazione di colonne AutoIncrement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 2548ad9382b406978dac0a3d366207626278f501
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205127"
---
# <a name="creating-autoincrement-columns"></a><span data-ttu-id="84d74-102">Creazione di colonne AutoIncrement</span><span class="sxs-lookup"><span data-stu-id="84d74-102">Creating AutoIncrement Columns</span></span>
<span data-ttu-id="84d74-103">Per assicurarsi che i valori contenuti in una colonna siano univoci, è possibile impostare l'incremento automatico dei valori di colonna a ogni aggiunta di nuove colonne alla tabella.</span><span class="sxs-lookup"><span data-stu-id="84d74-103">To ensure unique column values, you can set the column values to increment automatically when new rows are added to the table.</span></span> <span data-ttu-id="84d74-104">Per creare un incremento <xref:System.Data.DataColumn>automatico, impostare la <xref:System.Data.DataColumn.AutoIncrement%2A> proprietà della colonna su **true**.</span><span class="sxs-lookup"><span data-stu-id="84d74-104">To create an auto-incrementing <xref:System.Data.DataColumn>, set the <xref:System.Data.DataColumn.AutoIncrement%2A> property of the column to **true**.</span></span> <span data-ttu-id="84d74-105">Inizia quindi con il valore definito <xref:System.Data.DataColumn.AutoIncrementSeed%2A> nella proprietà e, a ogni riga aggiunta, il valore della colonna <xref:System.Data.DataColumn.AutoIncrementStep%2A> AutoIncrement aumenta in base al valore definito nella proprietà della colonna. <xref:System.Data.DataColumn></span><span class="sxs-lookup"><span data-stu-id="84d74-105">The <xref:System.Data.DataColumn> then starts with the value defined in the <xref:System.Data.DataColumn.AutoIncrementSeed%2A> property, and with each row added the value of the **AutoIncrement** column increases by the value defined in the <xref:System.Data.DataColumn.AutoIncrementStep%2A> property of the column.</span></span>  
  
 <span data-ttu-id="84d74-106">Per le colonne di **incremento automatico** è consigliabile impostare <xref:System.Data.DataColumn.ReadOnly%2A> la proprietà dell'oggetto **DataColumn** su **true**.</span><span class="sxs-lookup"><span data-stu-id="84d74-106">For **AutoIncrement** columns, we recommend that the <xref:System.Data.DataColumn.ReadOnly%2A> property of the **DataColumn** be set to **true**.</span></span>  
  
 <span data-ttu-id="84d74-107">Nell'esempio seguente viene illustrato come creare una colonna con valore iniziale pari a 200 e con incrementi in 3 passaggi.</span><span class="sxs-lookup"><span data-stu-id="84d74-107">The following example demonstrates how to create a column that starts with a value of 200 and adds incrementally in steps of 3.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="84d74-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84d74-108">See also</span></span>

- <xref:System.Data.DataColumn>
- [<span data-ttu-id="84d74-109">Definizione dello schema DataTable</span><span class="sxs-lookup"><span data-stu-id="84d74-109">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="84d74-110">DataTable</span><span class="sxs-lookup"><span data-stu-id="84d74-110">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="84d74-111">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="84d74-111">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
