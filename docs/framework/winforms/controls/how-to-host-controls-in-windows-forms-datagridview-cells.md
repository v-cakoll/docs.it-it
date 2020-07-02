---
title: Controlli host nelle celle DataGridView
description: Informazioni su come ospitare i controlli in Windows Forms celle DataGridView per consentire agli utenti di immettere e modificare i valori in diversi modi.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], hosting in cells
- DataGridView control [Windows Forms], hosting controls in cells
- cells [Windows Forms], hosting controls
ms.assetid: e79a9d4e-64ec-41f5-93ec-f5492633cbb2
ms.openlocfilehash: 87901cbf86689bec49f5692feeabdae79f6b93ba
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619546"
---
# <a name="how-to-host-controls-in-windows-forms-datagridview-cells"></a><span data-ttu-id="e147b-103">Procedura: inserire controlli in celle del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e147b-103">How to: Host Controls in Windows Forms DataGridView Cells</span></span>
<span data-ttu-id="e147b-104">Il controllo <xref:System.Windows.Forms.DataGridView> fornisce diversi tipi di colonna, consentendo agli utenti di immettere e modificare i valori in modi differenti.</span><span class="sxs-lookup"><span data-stu-id="e147b-104">The <xref:System.Windows.Forms.DataGridView> control provides several column types, enabling your users to enter and edit values in a variety of ways.</span></span> <span data-ttu-id="e147b-105">Tuttavia, se questi tipi di colonna non soddisfano le esigenze di immissione di dati, è possibile creare tipi di colonna personalizzati con celle che contengono i controlli host desiderati.</span><span class="sxs-lookup"><span data-stu-id="e147b-105">If these column types do not meet your data-entry needs, however, you can create your own column types with cells that host controls of your choosing.</span></span> <span data-ttu-id="e147b-106">A questo scopo è necessario definire classi derivanti dalle classi <xref:System.Windows.Forms.DataGridViewColumn> e <xref:System.Windows.Forms.DataGridViewCell>.</span><span class="sxs-lookup"><span data-stu-id="e147b-106">To do this, you must define classes that derive from <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewCell>.</span></span> <span data-ttu-id="e147b-107">È anche necessario definire una classe che derivi dalla classe <xref:System.Windows.Forms.Control> e implementi l'interfaccia <xref:System.Windows.Forms.IDataGridViewEditingControl>.</span><span class="sxs-lookup"><span data-stu-id="e147b-107">You must also define a class that derives from <xref:System.Windows.Forms.Control> and implements the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
 <span data-ttu-id="e147b-108">Nell'esempio di codice seguente viene illustrato come creare una colonna di calendario.</span><span class="sxs-lookup"><span data-stu-id="e147b-108">The following code example shows how to create a calendar column.</span></span> <span data-ttu-id="e147b-109">Le celle di questa colonna visualizzano le date in normali celle di caselle di testo, ma quanto l'utente modifica una cella, viene visualizzato un controllo <xref:System.Windows.Forms.DateTimePicker>.</span><span class="sxs-lookup"><span data-stu-id="e147b-109">The cells of this column display dates in ordinary text box cells, but when the user edits a cell, a <xref:System.Windows.Forms.DateTimePicker> control appears.</span></span> <span data-ttu-id="e147b-110">Per evitare di dover implementare di nuovo la funzionalità di visualizzazione delle caselle di testo, la classe `CalendarCell` deriva dalla classe <xref:System.Windows.Forms.DataGridViewTextBoxCell> invece di ereditare direttamente la classe <xref:System.Windows.Forms.DataGridViewCell>.</span><span class="sxs-lookup"><span data-stu-id="e147b-110">In order to avoid having to implement text box display functionality again, the `CalendarCell` class derives from the <xref:System.Windows.Forms.DataGridViewTextBoxCell> class rather than inheriting the <xref:System.Windows.Forms.DataGridViewCell> class directly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e147b-111">Quando si deriva dalla classe <xref:System.Windows.Forms.DataGridViewCell> o <xref:System.Windows.Forms.DataGridViewColumn> e si aggiungono nuove proprietà alla classe derivata, accertarsi di eseguire l'override del metodo `Clone` per copiare le nuove proprietà durante le operazioni di clonazione.</span><span class="sxs-lookup"><span data-stu-id="e147b-111">When you derive from <xref:System.Windows.Forms.DataGridViewCell> or <xref:System.Windows.Forms.DataGridViewColumn> and add new properties to the derived class, be sure to override the `Clone` method to copy the new properties during cloning operations.</span></span> <span data-ttu-id="e147b-112">È anche necessario chiamare il metodo `Clone` della classe base in modo che le proprietà della classe base vengano copiate nella nuova cella o colonna.</span><span class="sxs-lookup"><span data-stu-id="e147b-112">You should also call the base class's `Clone` method so that the properties of the base class are copied to the new cell or column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e147b-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="e147b-113">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCalendarColumn#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/CS/datagridviewcalendarcolumn.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewCalendarColumn#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/VB/datagridviewcalendarcolumn.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e147b-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="e147b-114">Compiling the Code</span></span>  
 <span data-ttu-id="e147b-115">Per l'esempio seguente sono necessari i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e147b-115">The following example requires:</span></span>  
  
- <span data-ttu-id="e147b-116">Riferimenti agli assembly System e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="e147b-116">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e147b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e147b-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewTextBoxCell>
- <xref:System.Windows.Forms.IDataGridViewEditingControl>
- <xref:System.Windows.Forms.DateTimePicker>
- [<span data-ttu-id="e147b-118">Personalizzazione del controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="e147b-118">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="e147b-119">Architettura del controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="e147b-119">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)
- [<span data-ttu-id="e147b-120">Tipi di colonna nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e147b-120">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
