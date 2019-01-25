---
title: 'Procedura: Ordinare il contenuto di un Windows Form ComboBox, ListBox o CheckedListBox (controllo)'
ms.date: 03/30/2017
helpviewer_keywords:
- CheckedListBox control [Windows Forms], sorting
- ComboBox control [Windows Forms], sorting contents
- combo boxes [Windows Forms], sorting contents
- list boxes [Windows Forms], sorting contents
- ListBox control [Windows Forms], sorting contents
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
ms.openlocfilehash: 97965dcef1541aec51ba57a7cf314730f892f141
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54686322"
---
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="e8110-102">Procedura: Ordinare il contenuto di un Windows Form ComboBox, ListBox o CheckedListBox (controllo)</span><span class="sxs-lookup"><span data-stu-id="e8110-102">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="e8110-103">Controlli Windows Form ordinamento non viene eseguito quando sono associati a dati.</span><span class="sxs-lookup"><span data-stu-id="e8110-103">Windows Forms controls do not sort when they are data-bound.</span></span> <span data-ttu-id="e8110-104">Per visualizzare i dati ordinati, utilizzare un'origine dati che supporta l'ordinamento e quindi chiedere l'origine dati di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="e8110-104">To display sorted data, use a data source that supports sorting and then have the data source sort it.</span></span> <span data-ttu-id="e8110-105">Le origini dati che supportano l'ordinamento sono visualizzazioni dei dati, dati consente di visualizzare i responsabili e matrici ordinate.</span><span class="sxs-lookup"><span data-stu-id="e8110-105">Data sources that support sorting are data views, data view managers, and sorted arrays.</span></span>  
  
 <span data-ttu-id="e8110-106">Se il controllo non è associato a dati, è possibile ordinarlo.</span><span class="sxs-lookup"><span data-stu-id="e8110-106">If the control is not data-bound, you can sort it.</span></span>  
  
### <a name="to-sort-the-list"></a><span data-ttu-id="e8110-107">Per ordinare l'elenco</span><span class="sxs-lookup"><span data-stu-id="e8110-107">To sort the list</span></span>  
  
1.  <span data-ttu-id="e8110-108">Impostare la proprietà `Sorted` su `true`.</span><span class="sxs-lookup"><span data-stu-id="e8110-108">Set the `Sorted` property to `true`.</span></span>  
  
     <span data-ttu-id="e8110-109">Questa impostazione Riposiziona tutti gli elementi dell'elenco in base all'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="e8110-109">This setting repositions all existing list items in sorted order.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8110-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8110-110">See also</span></span>
- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [<span data-ttu-id="e8110-111">Data binding in Windows Form</span><span class="sxs-lookup"><span data-stu-id="e8110-111">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)
- [<span data-ttu-id="e8110-112">Procedura: Aggiungere e rimuovere elementi da un Windows Form ComboBox, ListBox o CheckedListBox (controllo)</span><span class="sxs-lookup"><span data-stu-id="e8110-112">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)
- [<span data-ttu-id="e8110-113">Quando usare un controllo ComboBox Windows Form anziché un controllo ListBox</span><span class="sxs-lookup"><span data-stu-id="e8110-113">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [<span data-ttu-id="e8110-114">Controlli Windows Form usati per elencare opzioni</span><span class="sxs-lookup"><span data-stu-id="e8110-114">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
