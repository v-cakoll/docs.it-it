---
title: Creazione di colonne espressioni
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0af3bd64-92a2-4b47-ae62-f5df35f131a6
ms.openlocfilehash: 6e19e4e7cc0ea92e9d93e45c2a50d009e46b78c5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59175500"
---
# <a name="creating-expression-columns"></a><span data-ttu-id="f5f92-102">Creazione di colonne espressioni</span><span class="sxs-lookup"><span data-stu-id="f5f92-102">Creating Expression Columns</span></span>
<span data-ttu-id="f5f92-103">È possibile definire un'espressione per una colonna per consentire che questa contenga un valore calcolato sulla base di altri valori di colonna nella stessa riga o sulla base di valori di colonna di più righe della tabella.</span><span class="sxs-lookup"><span data-stu-id="f5f92-103">You can define an expression for a column, enabling it to contain a value calculated from other column values in the same row or from the column values of multiple rows in the table.</span></span> <span data-ttu-id="f5f92-104">Per definire l'espressione da valutare, usare la proprietà <xref:System.Data.DataColumn.Expression%2A> della colonna di destinazione e la proprietà <xref:System.Data.DataColumn.ColumnName%2A> per fare riferimento ad altre colonne nell'espressione.</span><span class="sxs-lookup"><span data-stu-id="f5f92-104">To define the expression to be evaluated, use the <xref:System.Data.DataColumn.Expression%2A> property of the target column, and use the <xref:System.Data.DataColumn.ColumnName%2A> property to refer to other columns in the expression.</span></span> <span data-ttu-id="f5f92-105">La proprietà <xref:System.Data.DataColumn.DataType%2A> specificata per la colonna di espressioni deve essere adeguata per il valore restituito dall'espressione.</span><span class="sxs-lookup"><span data-stu-id="f5f92-105">The <xref:System.Data.DataColumn.DataType%2A> for the expression column must be appropriate for the value that the expression returns.</span></span>  
  
 <span data-ttu-id="f5f92-106">La tabella seguente indica diversi usi possibili delle colonne di espressioni in una tabella.</span><span class="sxs-lookup"><span data-stu-id="f5f92-106">The following table lists several possible uses for expression columns in a table.</span></span>  
  
|<span data-ttu-id="f5f92-107">Tipo di espressione</span><span class="sxs-lookup"><span data-stu-id="f5f92-107">Expression type</span></span>|<span data-ttu-id="f5f92-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="f5f92-108">Example</span></span>|  
|---------------------|-------------|  
|<span data-ttu-id="f5f92-109">Confronto</span><span class="sxs-lookup"><span data-stu-id="f5f92-109">Comparison</span></span>|<span data-ttu-id="f5f92-110">"Total >= 500"</span><span class="sxs-lookup"><span data-stu-id="f5f92-110">"Total >= 500"</span></span>|  
|<span data-ttu-id="f5f92-111">Calcolo</span><span class="sxs-lookup"><span data-stu-id="f5f92-111">Computation</span></span>|<span data-ttu-id="f5f92-112">"UnitPrice \* Quantity"</span><span class="sxs-lookup"><span data-stu-id="f5f92-112">"UnitPrice \* Quantity"</span></span>|  
|<span data-ttu-id="f5f92-113">Aggregazione</span><span class="sxs-lookup"><span data-stu-id="f5f92-113">Aggregation</span></span>|<span data-ttu-id="f5f92-114">Sum(Price)</span><span class="sxs-lookup"><span data-stu-id="f5f92-114">Sum(Price)</span></span>|  
  
 <span data-ttu-id="f5f92-115">È possibile impostare il **espressione** proprietà su un oggetto esistente **DataColumn** oggetto oppure è possibile includere la proprietà come terzo argomento passato al <xref:System.Data.DataColumn> costruttore, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f5f92-115">You can set the **Expression** property on an existing **DataColumn** object, or you can include the property as the third argument passed to the <xref:System.Data.DataColumn> constructor, as shown in the following example.</span></span>  
  
```vb  
workTable.Columns.Add("Total",Type.GetType("System.Double"))  
workTable.Columns.Add("SalesTax", Type.GetType("System.Double"), _  
  "Total * 0.086")  
```  
  
```csharp  
workTable.Columns.Add("Total", typeof(Double));  
workTable.Columns.Add("SalesTax", typeof(Double), "Total * 0.086");  
```  
  
 <span data-ttu-id="f5f92-116">Le espressioni possono fare riferimento ad altre colonne di espressioni. Viene tuttavia generata un'eccezione se è presente un riferimento circolare, ovvero quando due espressioni fanno riferimento l'una all'altra.</span><span class="sxs-lookup"><span data-stu-id="f5f92-116">Expressions can reference other expression columns; however, a circular reference, in which two expressions reference each other, will generate an exception.</span></span> <span data-ttu-id="f5f92-117">Per informazioni sulla scrittura di espressioni, vedere la <xref:System.Data.DataColumn.Expression%2A> proprietà del **DataColumn** classe.</span><span class="sxs-lookup"><span data-stu-id="f5f92-117">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5f92-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5f92-118">See also</span></span>

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="f5f92-119">Definizione dello schema DataTable</span><span class="sxs-lookup"><span data-stu-id="f5f92-119">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)
- [<span data-ttu-id="f5f92-120">DataTable</span><span class="sxs-lookup"><span data-stu-id="f5f92-120">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [<span data-ttu-id="f5f92-121">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="f5f92-121">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
