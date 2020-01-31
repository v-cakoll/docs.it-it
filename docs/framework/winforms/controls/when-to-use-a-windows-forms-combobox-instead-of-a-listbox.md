---
title: ComboBox e ListBox
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox control [Windows Forms], adding and removing items
- ListBox control [Windows Forms], vs. ComboBox
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- ComboBox control [Windows Forms], compared to ListBox
- combo boxes [Windows Forms], compared to list boxes
- ListBox control [Windows Forms], accessing items
- ListCount property
ms.assetid: 7bcaea58-1cfa-46db-9baf-b75a69d8f9ec
ms.openlocfilehash: 7087760a393bb58d83d899c1741c745fb28585bb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739933"
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a><span data-ttu-id="66590-102">Quando utilizzare un controllo ComboBox Windows Form anziché un controllo ListBox</span><span class="sxs-lookup"><span data-stu-id="66590-102">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>
<span data-ttu-id="66590-103">I controlli <xref:System.Windows.Forms.ComboBox> e <xref:System.Windows.Forms.ListBox> hanno comportamenti simili e in alcuni casi possono essere intercambiabili.</span><span class="sxs-lookup"><span data-stu-id="66590-103">The <xref:System.Windows.Forms.ComboBox> and the <xref:System.Windows.Forms.ListBox> controls have similar behaviors, and in some cases may be interchangeable.</span></span> <span data-ttu-id="66590-104">In alcuni casi, tuttavia, una o l'altra è più appropriata per un'attività.</span><span class="sxs-lookup"><span data-stu-id="66590-104">There are times, however, when one or the other is more appropriate to a task.</span></span>  
  
 <span data-ttu-id="66590-105">In genere, una casella combinata è appropriata quando è presente un elenco di scelte consigliate e una casella di riepilogo è appropriata quando si desidera limitare l'input a quello presente nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="66590-105">Generally, a combo box is appropriate when there is a list of suggested choices, and a list box is appropriate when you want to limit input to what is on the list.</span></span> <span data-ttu-id="66590-106">Una casella combinata contiene un campo casella di testo, quindi le scelte non presenti nell'elenco possono essere digitate.</span><span class="sxs-lookup"><span data-stu-id="66590-106">A combo box contains a text box field, so choices not on the list can be typed in.</span></span> <span data-ttu-id="66590-107">L'eccezione si verifica quando la proprietà <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> è impostata su <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span><span class="sxs-lookup"><span data-stu-id="66590-107">The exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span></span> <span data-ttu-id="66590-108">In tal caso, il controllo selezionerà un elemento se si digita la prima lettera.</span><span class="sxs-lookup"><span data-stu-id="66590-108">In that case, the control will select an item if you type its first letter.</span></span>  
  
 <span data-ttu-id="66590-109">Inoltre, le caselle combinate salvano lo spazio in un form.</span><span class="sxs-lookup"><span data-stu-id="66590-109">In addition, combo boxes save space on a form.</span></span> <span data-ttu-id="66590-110">Poiché l'elenco completo non viene visualizzato fino a quando l'utente non fa clic sulla freccia verso il basso, una casella combinata può facilmente rientrare in uno spazio ridotto in cui una casella di riepilogo non è adatta.</span><span class="sxs-lookup"><span data-stu-id="66590-110">Because the full list is not displayed until the user clicks the down arrow, a combo box can easily fit in a small space where a list box would not fit.</span></span> <span data-ttu-id="66590-111">Si verifica un'eccezione quando la proprietà <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> è impostata su <xref:System.Windows.Forms.ComboBoxStyle.Simple>: viene visualizzato l'elenco completo e la casella combinata occupa più spazio rispetto a una casella di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="66590-111">An exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.Simple>: the full list is displayed, and the combo box takes up more room than a list box would.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66590-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66590-112">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="66590-113">Procedura: Aggiungere e rimuovere elementi da un controllo ComboBox, ListBox o CheckedListBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="66590-113">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](add-and-remove-items-from-a-wf-combobox.md)
- [<span data-ttu-id="66590-114">Procedura: Ordinare il contenuto di un controllo ComboBox, ListBox o CheckedListBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="66590-114">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [<span data-ttu-id="66590-115">Controlli Windows Form usati per elencare opzioni</span><span class="sxs-lookup"><span data-stu-id="66590-115">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
