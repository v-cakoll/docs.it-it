---
title: 'Procedura: Aggiungere una colonna non associata a un controllo DataGridView di Windows Forms associato ai dati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], unbound data
- data grids [Windows Forms], adding unbound columns
- DataGridView control [Windows Forms], unbound data
ms.assetid: f7bdc4d8-ba8e-421b-ad62-82d936f01372
ms.openlocfilehash: d40eea54d908f17fc2fe893d5bc15a073a066ba1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651584"
---
# <a name="how-to-add-an-unbound-column-to-a-data-bound-windows-forms-datagridview-control"></a><span data-ttu-id="5c9f8-102">Procedura: Aggiungere una colonna non associata a un controllo DataGridView di Windows Forms associato ai dati</span><span class="sxs-lookup"><span data-stu-id="5c9f8-102">How to: Add an Unbound Column to a Data-Bound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="5c9f8-103">I dati visualizzati nel controllo <xref:System.Windows.Forms.DataGridView> in genere provengono da un'origine dati di qualche tipo, ma è possibile visualizzare una colonna di dati di origine diversa.</span><span class="sxs-lookup"><span data-stu-id="5c9f8-103">The data you display in the <xref:System.Windows.Forms.DataGridView> control will normally come from a data source of some kind, but you might want to display a column of data that does not come from the data source.</span></span> <span data-ttu-id="5c9f8-104">Questo tipo di colonna è detto colonna non associata.</span><span class="sxs-lookup"><span data-stu-id="5c9f8-104">This kind of column is called an unbound column.</span></span> <span data-ttu-id="5c9f8-105">Le colonne non associate possono assumere molte forme.</span><span class="sxs-lookup"><span data-stu-id="5c9f8-105">Unbound columns can take many forms.</span></span> <span data-ttu-id="5c9f8-106">Spesso vengono usate per fornire accesso ai dettagli di una riga di dati.</span><span class="sxs-lookup"><span data-stu-id="5c9f8-106">Frequently, they are used to provide access to the details of a data row.</span></span>  
  
 <span data-ttu-id="5c9f8-107">Esempio di codice seguente viene illustrato come creare una colonna non associata di **dettagli** pulsanti da visualizzare una tabella figlio correlata a una determinata riga in una tabella padre quando si implementa uno scenario master-details.</span><span class="sxs-lookup"><span data-stu-id="5c9f8-107">The following code example demonstrates how to create an unbound column of **Details** buttons to display a child table related to a particular row in a parent table when you implement a master/detail scenario.</span></span> <span data-ttu-id="5c9f8-108">Per rispondere alle selezioni dei pulsanti, implementare un gestore dell'evento <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> che visualizzi un form contenente la tabella figlio.</span><span class="sxs-lookup"><span data-stu-id="5c9f8-108">To respond to button clicks, implement a <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> event handler that displays a form containing the child table.</span></span>  
  
 <span data-ttu-id="5c9f8-109">Questa attività è supportata in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5c9f8-109">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="5c9f8-110">Vedere anche [come: Aggiungere e rimuovere colonne nel Windows Form controllo DataGridView utilizzando la finestra di progettazione](add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="5c9f8-110">Also see [How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer](add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c9f8-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="5c9f8-111">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#010](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#010)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#010](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#010)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5c9f8-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="5c9f8-112">Compiling the Code</span></span>  
 <span data-ttu-id="5c9f8-113">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5c9f8-113">This example requires:</span></span>  
  
- <span data-ttu-id="5c9f8-114">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="5c9f8-114">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="5c9f8-115">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5c9f8-115">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c9f8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c9f8-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="5c9f8-117">Visualizzazione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="5c9f8-117">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="5c9f8-118">Modalità di visualizzazione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="5c9f8-118">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)
