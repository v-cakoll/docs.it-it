---
title: Controlli host nelle celle DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], hosting in cells
- DataGridView control [Windows Forms], hosting controls in cells
- cells [Windows Forms], hosting controls
ms.assetid: e79a9d4e-64ec-41f5-93ec-f5492633cbb2
ms.openlocfilehash: a64521a15a272ca8140302f39d15e7f17e0c423b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736532"
---
# <a name="how-to-host-controls-in-windows-forms-datagridview-cells"></a><span data-ttu-id="d78b8-102">Procedura: inserire controlli in celle del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="d78b8-102">How to: Host Controls in Windows Forms DataGridView Cells</span></span>
<span data-ttu-id="d78b8-103">Il controllo <xref:System.Windows.Forms.DataGridView> fornisce diversi tipi di colonna, consentendo agli utenti di immettere e modificare i valori in modi differenti.</span><span class="sxs-lookup"><span data-stu-id="d78b8-103">The <xref:System.Windows.Forms.DataGridView> control provides several column types, enabling your users to enter and edit values in a variety of ways.</span></span> <span data-ttu-id="d78b8-104">Tuttavia, se questi tipi di colonna non soddisfano le esigenze di immissione di dati, è possibile creare tipi di colonna personalizzati con celle che contengono i controlli host desiderati.</span><span class="sxs-lookup"><span data-stu-id="d78b8-104">If these column types do not meet your data-entry needs, however, you can create your own column types with cells that host controls of your choosing.</span></span> <span data-ttu-id="d78b8-105">A questo scopo è necessario definire classi derivanti dalle classi <xref:System.Windows.Forms.DataGridViewColumn> e <xref:System.Windows.Forms.DataGridViewCell>.</span><span class="sxs-lookup"><span data-stu-id="d78b8-105">To do this, you must define classes that derive from <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewCell>.</span></span> <span data-ttu-id="d78b8-106">È anche necessario definire una classe che derivi dalla classe <xref:System.Windows.Forms.Control> e implementi l'interfaccia <xref:System.Windows.Forms.IDataGridViewEditingControl>.</span><span class="sxs-lookup"><span data-stu-id="d78b8-106">You must also define a class that derives from <xref:System.Windows.Forms.Control> and implements the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
 <span data-ttu-id="d78b8-107">Nell'esempio di codice seguente viene illustrato come creare una colonna di calendario.</span><span class="sxs-lookup"><span data-stu-id="d78b8-107">The following code example shows how to create a calendar column.</span></span> <span data-ttu-id="d78b8-108">Le celle di questa colonna visualizzano le date in normali celle di caselle di testo, ma quanto l'utente modifica una cella, viene visualizzato un controllo <xref:System.Windows.Forms.DateTimePicker>.</span><span class="sxs-lookup"><span data-stu-id="d78b8-108">The cells of this column display dates in ordinary text box cells, but when the user edits a cell, a <xref:System.Windows.Forms.DateTimePicker> control appears.</span></span> <span data-ttu-id="d78b8-109">Per evitare di dover implementare di nuovo la funzionalità di visualizzazione delle caselle di testo, la classe `CalendarCell` deriva dalla classe <xref:System.Windows.Forms.DataGridViewTextBoxCell> invece di ereditare direttamente la classe <xref:System.Windows.Forms.DataGridViewCell>.</span><span class="sxs-lookup"><span data-stu-id="d78b8-109">In order to avoid having to implement text box display functionality again, the `CalendarCell` class derives from the <xref:System.Windows.Forms.DataGridViewTextBoxCell> class rather than inheriting the <xref:System.Windows.Forms.DataGridViewCell> class directly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d78b8-110">Quando si deriva dalla classe <xref:System.Windows.Forms.DataGridViewCell> o <xref:System.Windows.Forms.DataGridViewColumn> e si aggiungono nuove proprietà alla classe derivata, accertarsi di eseguire l'override del metodo `Clone` per copiare le nuove proprietà durante le operazioni di clonazione.</span><span class="sxs-lookup"><span data-stu-id="d78b8-110">When you derive from <xref:System.Windows.Forms.DataGridViewCell> or <xref:System.Windows.Forms.DataGridViewColumn> and add new properties to the derived class, be sure to override the `Clone` method to copy the new properties during cloning operations.</span></span> <span data-ttu-id="d78b8-111">È anche necessario chiamare il metodo `Clone` della classe base in modo che le proprietà della classe base vengano copiate nella nuova cella o colonna.</span><span class="sxs-lookup"><span data-stu-id="d78b8-111">You should also call the base class's `Clone` method so that the properties of the base class are copied to the new cell or column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d78b8-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="d78b8-112">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCalendarColumn#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/CS/datagridviewcalendarcolumn.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewCalendarColumn#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/VB/datagridviewcalendarcolumn.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d78b8-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="d78b8-113">Compiling the Code</span></span>  
 <span data-ttu-id="d78b8-114">Per l'esempio seguente sono necessari i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d78b8-114">The following example requires:</span></span>  
  
- <span data-ttu-id="d78b8-115">Riferimenti agli assembly System e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="d78b8-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d78b8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d78b8-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewTextBoxCell>
- <xref:System.Windows.Forms.IDataGridViewEditingControl>
- <xref:System.Windows.Forms.DateTimePicker>
- [<span data-ttu-id="d78b8-117">Personalizzazione del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="d78b8-117">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="d78b8-118">Architettura del controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="d78b8-118">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)
- [<span data-ttu-id="d78b8-119">Tipi di colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="d78b8-119">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
