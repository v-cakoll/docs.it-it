---
title: "Quando utilizzare un controllo ComboBox Windows Form anziché un controllo ListBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8c4a2886dae3aee147d80957874d0d98714c0ca5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a><span data-ttu-id="f1b14-102">Quando utilizzare un controllo ComboBox Windows Form anziché un controllo ListBox</span><span class="sxs-lookup"><span data-stu-id="f1b14-102">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>
<span data-ttu-id="f1b14-103">Il <xref:System.Windows.Forms.ComboBox> e <xref:System.Windows.Forms.ListBox> controlli presentano comportamenti simili e in alcuni casi potrebbe essere intercambiabili.</span><span class="sxs-lookup"><span data-stu-id="f1b14-103">The <xref:System.Windows.Forms.ComboBox> and the <xref:System.Windows.Forms.ListBox> controls have similar behaviors, and in some cases may be interchangeable.</span></span> <span data-ttu-id="f1b14-104">Esistono casi, tuttavia, quando una o l'altra è più appropriata per un'attività.</span><span class="sxs-lookup"><span data-stu-id="f1b14-104">There are times, however, when one or the other is more appropriate to a task.</span></span>  
  
 <span data-ttu-id="f1b14-105">In genere, una casella combinata è appropriata quando è disponibile un elenco di opzioni disponibili, e una casella di riepilogo è appropriata quando si desidera limitare l'input ai quali è presente nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="f1b14-105">Generally, a combo box is appropriate when there is a list of suggested choices, and a list box is appropriate when you want to limit input to what is on the list.</span></span> <span data-ttu-id="f1b14-106">Una casella combinata contiene un campo di casella di testo, pertanto possono essere digitate opzioni non presenti nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="f1b14-106">A combo box contains a text box field, so choices not on the list can be typed in.</span></span> <span data-ttu-id="f1b14-107">L'eccezione si verifica quando il <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> è impostata su <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span><span class="sxs-lookup"><span data-stu-id="f1b14-107">The exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span></span> <span data-ttu-id="f1b14-108">In tal caso, il controllo verrà selezionare un elemento, se si digita la prima lettera.</span><span class="sxs-lookup"><span data-stu-id="f1b14-108">In that case, the control will select an item if you type its first letter.</span></span>  
  
 <span data-ttu-id="f1b14-109">Inoltre, le caselle combinate di risparmiare spazio in un form.</span><span class="sxs-lookup"><span data-stu-id="f1b14-109">In addition, combo boxes save space on a form.</span></span> <span data-ttu-id="f1b14-110">Poiché non è visualizzato l'elenco completo fino a quando l'utente fa clic sulla freccia rivolta verso il basso, una casella combinata può essere inserita in uno spazio ridotto, in cui non sarebbe sufficienti per una casella di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="f1b14-110">Because the full list is not displayed until the user clicks the down arrow, a combo box can easily fit in a small space where a list box would not fit.</span></span> <span data-ttu-id="f1b14-111">Un'eccezione si verifica quando il <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> è impostata su <xref:System.Windows.Forms.ComboBoxStyle.Simple>: viene visualizzato l'elenco completo e la casella combinata occupa più spazio rispetto a una casella di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="f1b14-111">An exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.Simple>: the full list is displayed, and the combo box takes up more room than a list box would.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1b14-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1b14-112">See Also</span></span>  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 [<span data-ttu-id="f1b14-113">Procedura: Aggiungere e rimuovere elementi da un controllo ComboBox, ListBox o CheckedListBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="f1b14-113">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [<span data-ttu-id="f1b14-114">Procedura: Ordinare il contenuto di un controllo ComboBox, ListBox o CheckedListBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="f1b14-114">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 [<span data-ttu-id="f1b14-115">Controlli Windows Form usati per elencare opzioni</span><span class="sxs-lookup"><span data-stu-id="f1b14-115">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
