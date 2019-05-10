---
title: 'Procedura: Ospitare controlli nelle celle DataGridView di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], hosting in cells
- DataGridView control [Windows Forms], hosting controls in cells
- cells [Windows Forms], hosting controls
ms.assetid: e79a9d4e-64ec-41f5-93ec-f5492633cbb2
ms.openlocfilehash: d2e0c4106ca4d0409c42ed51fa454252234079d4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623002"
---
# <a name="how-to-host-controls-in-windows-forms-datagridview-cells"></a><span data-ttu-id="60072-102">Procedura: Ospitare controlli nelle celle DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="60072-102">How to: Host Controls in Windows Forms DataGridView Cells</span></span>
<span data-ttu-id="60072-103">Il controllo <xref:System.Windows.Forms.DataGridView> fornisce diversi tipi di colonna, consentendo agli utenti di immettere e modificare i valori in modi differenti.</span><span class="sxs-lookup"><span data-stu-id="60072-103">The <xref:System.Windows.Forms.DataGridView> control provides several column types, enabling your users to enter and edit values in a variety of ways.</span></span> <span data-ttu-id="60072-104">Tuttavia, se questi tipi di colonna non soddisfano le esigenze di immissione di dati, è possibile creare tipi di colonna personalizzati con celle che contengono i controlli desiderati.</span><span class="sxs-lookup"><span data-stu-id="60072-104">If these column types do not meet your data-entry needs, however, you can create your own column types with cells that host controls of your choosing.</span></span> <span data-ttu-id="60072-105">A questo scopo è necessario definire classi derivanti dalle classi <xref:System.Windows.Forms.DataGridViewColumn> e <xref:System.Windows.Forms.DataGridViewCell>.</span><span class="sxs-lookup"><span data-stu-id="60072-105">To do this, you must define classes that derive from <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewCell>.</span></span> <span data-ttu-id="60072-106">È anche necessario definire una classe che derivi dalla classe <xref:System.Windows.Forms.Control> e implementi l'interfaccia <xref:System.Windows.Forms.IDataGridViewEditingControl>.</span><span class="sxs-lookup"><span data-stu-id="60072-106">You must also define a class that derives from <xref:System.Windows.Forms.Control> and implements the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
 <span data-ttu-id="60072-107">Nell'esempio di codice seguente viene illustrato come creare una colonna di calendario.</span><span class="sxs-lookup"><span data-stu-id="60072-107">The following code example shows how to create a calendar column.</span></span> <span data-ttu-id="60072-108">Le celle di questa colonna visualizzano le date in normali celle di caselle di testo, ma quanto l'utente modifica una cella, viene visualizzato un controllo <xref:System.Windows.Forms.DateTimePicker>.</span><span class="sxs-lookup"><span data-stu-id="60072-108">The cells of this column display dates in ordinary text box cells, but when the user edits a cell, a <xref:System.Windows.Forms.DateTimePicker> control appears.</span></span> <span data-ttu-id="60072-109">Per evitare di dover implementare di nuovo la funzionalità di visualizzazione delle caselle di testo, la classe `CalendarCell` deriva dalla classe <xref:System.Windows.Forms.DataGridViewTextBoxCell> invece di ereditare direttamente la classe <xref:System.Windows.Forms.DataGridViewCell>.</span><span class="sxs-lookup"><span data-stu-id="60072-109">In order to avoid having to implement text box display functionality again, the `CalendarCell` class derives from the <xref:System.Windows.Forms.DataGridViewTextBoxCell> class rather than inheriting the <xref:System.Windows.Forms.DataGridViewCell> class directly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60072-110">Quando si deriva dalla classe <xref:System.Windows.Forms.DataGridViewCell> o <xref:System.Windows.Forms.DataGridViewColumn> e si aggiungono nuove proprietà alla classe derivata, accertarsi di eseguire l'override del metodo `Clone` per copiare le nuove proprietà durante le operazioni di clonazione.</span><span class="sxs-lookup"><span data-stu-id="60072-110">When you derive from <xref:System.Windows.Forms.DataGridViewCell> or <xref:System.Windows.Forms.DataGridViewColumn> and add new properties to the derived class, be sure to override the `Clone` method to copy the new properties during cloning operations.</span></span> <span data-ttu-id="60072-111">È anche necessario chiamare il metodo `Clone` della classe base in modo che le proprietà della classe base vengano copiate nella nuova cella o colonna.</span><span class="sxs-lookup"><span data-stu-id="60072-111">You should also call the base class's `Clone` method so that the properties of the base class are copied to the new cell or column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60072-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="60072-112">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCalendarColumn#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/CS/datagridviewcalendarcolumn.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewCalendarColumn#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/VB/datagridviewcalendarcolumn.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="60072-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="60072-113">Compiling the Code</span></span>  
 <span data-ttu-id="60072-114">Per l'esempio seguente sono necessari i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="60072-114">The following example requires:</span></span>  
  
- <span data-ttu-id="60072-115">Riferimenti agli assembly System e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="60072-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="60072-116">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="60072-116">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="60072-117">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="60072-117">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60072-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60072-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewTextBoxCell>
- <xref:System.Windows.Forms.IDataGridViewEditingControl>
- <xref:System.Windows.Forms.DateTimePicker>
- [<span data-ttu-id="60072-119">Personalizzazione del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="60072-119">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="60072-120">Architettura del controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="60072-120">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)
- [<span data-ttu-id="60072-121">Tipi di colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="60072-121">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
