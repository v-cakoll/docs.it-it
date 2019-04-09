---
title: Quando utilizzare un controllo ComboBox Windows Form anziché un controllo ListBox
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
ms.openlocfilehash: 8a2429049acf1a22edde8d132ece17da4e91f1db
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111423"
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a><span data-ttu-id="bd7c8-102">Quando utilizzare un controllo ComboBox Windows Form anziché un controllo ListBox</span><span class="sxs-lookup"><span data-stu-id="bd7c8-102">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>
<span data-ttu-id="bd7c8-103">Il <xref:System.Windows.Forms.ComboBox> e il <xref:System.Windows.Forms.ListBox> controlli presentano comportamenti simili e in alcuni casi potrebbe essere intercambiabili.</span><span class="sxs-lookup"><span data-stu-id="bd7c8-103">The <xref:System.Windows.Forms.ComboBox> and the <xref:System.Windows.Forms.ListBox> controls have similar behaviors, and in some cases may be interchangeable.</span></span> <span data-ttu-id="bd7c8-104">Esistono casi, tuttavia, quando uno o l'altro è più appropriato per un'attività.</span><span class="sxs-lookup"><span data-stu-id="bd7c8-104">There are times, however, when one or the other is more appropriate to a task.</span></span>  
  
 <span data-ttu-id="bd7c8-105">In generale, una casella combinata è appropriata quando è disponibile un elenco di opzioni disponibili e una casella di riepilogo è appropriata quando si desidera limitare l'input ai quali è presente nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="bd7c8-105">Generally, a combo box is appropriate when there is a list of suggested choices, and a list box is appropriate when you want to limit input to what is on the list.</span></span> <span data-ttu-id="bd7c8-106">Una casella combinata contiene un campo casella di testo, in modo che le scelte non inclusi nell'elenco possono essere digitate.</span><span class="sxs-lookup"><span data-stu-id="bd7c8-106">A combo box contains a text box field, so choices not on the list can be typed in.</span></span> <span data-ttu-id="bd7c8-107">L'eccezione è quando il <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> è impostata su <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span><span class="sxs-lookup"><span data-stu-id="bd7c8-107">The exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span></span> <span data-ttu-id="bd7c8-108">In tal caso, il controllo selezionerà un elemento se si digita la prima lettera.</span><span class="sxs-lookup"><span data-stu-id="bd7c8-108">In that case, the control will select an item if you type its first letter.</span></span>  
  
 <span data-ttu-id="bd7c8-109">Inoltre, le caselle combinate di risparmiare spazio in un form.</span><span class="sxs-lookup"><span data-stu-id="bd7c8-109">In addition, combo boxes save space on a form.</span></span> <span data-ttu-id="bd7c8-110">Poiché non viene visualizzato l'elenco completo fino a quando l'utente fa clic sulla freccia in giù, una casella combinata può essere inserita in uno spazio ridotto, in cui non sarebbe sufficienti per una casella di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="bd7c8-110">Because the full list is not displayed until the user clicks the down arrow, a combo box can easily fit in a small space where a list box would not fit.</span></span> <span data-ttu-id="bd7c8-111">Un'eccezione è quando il <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> è impostata su <xref:System.Windows.Forms.ComboBoxStyle.Simple>: viene visualizzato l'elenco completo e la casella combinata occupa più spazio rispetto a una casella di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="bd7c8-111">An exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.Simple>: the full list is displayed, and the combo box takes up more room than a list box would.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd7c8-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd7c8-112">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="bd7c8-113">Procedura: Aggiungere e rimuovere elementi da un controllo ComboBox, ListBox o CheckedListBox di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bd7c8-113">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](add-and-remove-items-from-a-wf-combobox.md)
- [<span data-ttu-id="bd7c8-114">Procedura: Ordinare il contenuto di un controllo ComboBox, ListBox o CheckedListBox di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bd7c8-114">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [<span data-ttu-id="bd7c8-115">Controlli Windows Form usati per elencare opzioni</span><span class="sxs-lookup"><span data-stu-id="bd7c8-115">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
