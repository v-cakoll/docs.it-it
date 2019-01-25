---
title: "Procedura: Modificare l'ordine delle colonne nel controllo DataGridView Windows Form"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], changing order
- DataGridView control [Windows Forms], column order
- data grids [Windows Forms], changing column order
ms.assetid: 5e9ac3bc-b0f0-48cb-a3d5-b005af905395
ms.openlocfilehash: 8e090bcafb66f2d6a997f9b54626d1bf23d7032e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54649518"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="e7aec-102">Procedura: Modificare l'ordine delle colonne nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="e7aec-102">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="e7aec-103">Quando si usa <xref:System.Windows.Forms.DataGridView> per visualizzare i dati di un'origine dati, a volte le colonne nello schema dell'origine dati non appaiono nell'ordine desiderato.</span><span class="sxs-lookup"><span data-stu-id="e7aec-103">When you use a <xref:System.Windows.Forms.DataGridView> to display data from a data source, the columns in the data source's schema sometimes do not appear in the order you would like to display them.</span></span> <span data-ttu-id="e7aec-104">È possibile modificare l'ordine di visualizzazione delle colonne usando la proprietà <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A> della classe <xref:System.Windows.Forms.DataGridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="e7aec-104">You can change the displayed order of the columns by using the <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A> property of the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
 <span data-ttu-id="e7aec-105">L'esempio di codice seguente riposiziona alcune colonne generate automaticamente durante l'associazione alla tabella Customers nel database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="e7aec-105">The following code example repositions some of the columns automatically generated when binding to the Customers table in the Northwind sample database.</span></span> <span data-ttu-id="e7aec-106">Per altre informazioni su come associare le <xref:System.Windows.Forms.DataGridView> il controllo a una tabella di database, vedere [come: Associare i dati per i Windows Form controllo DataGridView](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="e7aec-106">For more information about how to bind the <xref:System.Windows.Forms.DataGridView> control to a database table, see [How to: Bind Data to the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="e7aec-107">Questa attività è supportata in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e7aec-107">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="e7aec-108">Vedere anche [come: Modificare l'ordine delle colonne nel controllo DataGridView Windows Form usando la finestra di progettazione](https://msdn.microsoft.com/library/hb1dk7ax\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="e7aec-108">Also see [How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer](https://msdn.microsoft.com/library/hb1dk7ax\(v=vs.110\))</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7aec-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="e7aec-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#040](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#040)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#040](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#040)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e7aec-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="e7aec-110">Compiling the Code</span></span>  
 <span data-ttu-id="e7aec-111">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e7aec-111">This example requires:</span></span>  
  
-   <span data-ttu-id="e7aec-112">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `customersDataGridView` associato a una tabella con indicati i nomi di colonna, ad esempio la tabella `Customers` nel database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="e7aec-112">A <xref:System.Windows.Forms.DataGridView> control named `customersDataGridView` that is bound to a table with the indicated column names, such as the `Customers` table in the Northwind sample database.</span></span>  
  
-   <span data-ttu-id="e7aec-113">Riferimenti agli assembly <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType> e <xref:System.Xml?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e7aec-113">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType>, and <xref:System.Xml?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7aec-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7aec-114">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e7aec-115">Visualizzazione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e7aec-115">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="e7aec-116">Procedura: Associare dati al controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="e7aec-116">How to: Bind Data to the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)
