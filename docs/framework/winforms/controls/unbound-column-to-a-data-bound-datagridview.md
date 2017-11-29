---
title: 'Procedura: aggiungere una colonna non associata a un controllo DataGridView di Windows Form associato ai dati'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], unbound data
- data grids [Windows Forms], adding unbound columns
- DataGridView control [Windows Forms], unbound data
ms.assetid: f7bdc4d8-ba8e-421b-ad62-82d936f01372
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2cd6a1494a98d912469f7e45c7751a0a9741ff17
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-an-unbound-column-to-a-data-bound-windows-forms-datagridview-control"></a><span data-ttu-id="c27ef-102">Procedura: aggiungere una colonna non associata a un controllo DataGridView di Windows Form associato ai dati</span><span class="sxs-lookup"><span data-stu-id="c27ef-102">How to: Add an Unbound Column to a Data-Bound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="c27ef-103">I dati visualizzati nel controllo <xref:System.Windows.Forms.DataGridView> in genere provengono da un'origine dati di qualche tipo, ma è possibile visualizzare una colonna di dati di origine diversa.</span><span class="sxs-lookup"><span data-stu-id="c27ef-103">The data you display in the <xref:System.Windows.Forms.DataGridView> control will normally come from a data source of some kind, but you might want to display a column of data that does not come from the data source.</span></span> <span data-ttu-id="c27ef-104">Questo tipo di colonna è detto colonna non associata.</span><span class="sxs-lookup"><span data-stu-id="c27ef-104">This kind of column is called an unbound column.</span></span> <span data-ttu-id="c27ef-105">Le colonne non associate possono assumere molte forme.</span><span class="sxs-lookup"><span data-stu-id="c27ef-105">Unbound columns can take many forms.</span></span> <span data-ttu-id="c27ef-106">Spesso vengono usate per fornire accesso ai dettagli di una riga di dati.</span><span class="sxs-lookup"><span data-stu-id="c27ef-106">Frequently, they are used to provide access to the details of a data row.</span></span>  
  
 <span data-ttu-id="c27ef-107">Esempio di codice riportato di seguito viene illustrato come creare una colonna non associata di **dettagli** pulsanti da visualizzare una tabella figlio correlata a una determinata riga in una tabella padre quando si implementa uno scenario master-details.</span><span class="sxs-lookup"><span data-stu-id="c27ef-107">The following code example demonstrates how to create an unbound column of **Details** buttons to display a child table related to a particular row in a parent table when you implement a master/detail scenario.</span></span> <span data-ttu-id="c27ef-108">Per rispondere alle selezioni dei pulsanti, implementare un gestore dell'evento <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> che visualizzi un form contenente la tabella figlio.</span><span class="sxs-lookup"><span data-stu-id="c27ef-108">To respond to button clicks, implement a <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> event handler that displays a form containing the child table.</span></span>  
  
 <span data-ttu-id="c27ef-109">Questa attività è supportata in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c27ef-109">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="c27ef-110">Vedere anche [procedura: aggiungere e rimuovere colonne in cui il controllo Windows Form DataGridView usando la finestra di progettazione](http://msdn.microsoft.com/library/dyyesckz\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="c27ef-110">Also see [How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer](http://msdn.microsoft.com/library/dyyesckz\(v=vs.110\))</span></span>  
  
## <a name="example"></a><span data-ttu-id="c27ef-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="c27ef-111">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#010](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#010)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#010](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#010)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c27ef-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="c27ef-112">Compiling the Code</span></span>  
 <span data-ttu-id="c27ef-113">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c27ef-113">This example requires:</span></span>  
  
-   <span data-ttu-id="c27ef-114">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="c27ef-114">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="c27ef-115">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c27ef-115">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c27ef-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c27ef-116">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="c27ef-117">Visualizzazione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="c27ef-117">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="c27ef-118">Modalità di visualizzazione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="c27ef-118">Data Display Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)
