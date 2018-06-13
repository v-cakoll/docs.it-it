---
title: 'Procedura: ordinare il contenuto di un controllo ComboBox, ListBox o CheckedListBox Windows Form'
ms.date: 03/30/2017
helpviewer_keywords:
- CheckedListBox control [Windows Forms], sorting
- ComboBox control [Windows Forms], sorting contents
- combo boxes [Windows Forms], sorting contents
- list boxes [Windows Forms], sorting contents
- ListBox control [Windows Forms], sorting contents
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
ms.openlocfilehash: 8b8f9c7ad0ad7d3bbb7f3eeffd44e555207b82c4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535646"
---
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="2d685-102">Procedura: ordinare il contenuto di un controllo ComboBox, ListBox o CheckedListBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="2d685-102">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="2d685-103">Controlli Windows Form ordinamento non viene eseguito quando sono associati a dati.</span><span class="sxs-lookup"><span data-stu-id="2d685-103">Windows Forms controls do not sort when they are data-bound.</span></span> <span data-ttu-id="2d685-104">Per visualizzare i dati ordinati, utilizzare un'origine dati che supporta l'ordinamento e quindi chiedere l'origine dati di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="2d685-104">To display sorted data, use a data source that supports sorting and then have the data source sort it.</span></span> <span data-ttu-id="2d685-105">Origini dati che supportano l'ordinamento sono viste di dati, gestori di visualizzazioni dati e matrici ordinate.</span><span class="sxs-lookup"><span data-stu-id="2d685-105">Data sources that support sorting are data views, data view managers, and sorted arrays.</span></span>  
  
 <span data-ttu-id="2d685-106">Se il controllo non è associato a dati, è possibile ordinarli.</span><span class="sxs-lookup"><span data-stu-id="2d685-106">If the control is not data-bound, you can sort it.</span></span>  
  
### <a name="to-sort-the-list"></a><span data-ttu-id="2d685-107">Per ordinare l'elenco</span><span class="sxs-lookup"><span data-stu-id="2d685-107">To sort the list</span></span>  
  
1.  <span data-ttu-id="2d685-108">Impostare la proprietà `Sorted` su `true`.</span><span class="sxs-lookup"><span data-stu-id="2d685-108">Set the `Sorted` property to `true`.</span></span>  
  
     <span data-ttu-id="2d685-109">Questa impostazione Riposiziona tutti gli elementi dell'elenco in base all'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="2d685-109">This setting repositions all existing list items in sorted order.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d685-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d685-110">See Also</span></span>  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 <xref:System.Windows.Forms.CheckedListBox>  
 [<span data-ttu-id="2d685-111">Data binding in Windows Form</span><span class="sxs-lookup"><span data-stu-id="2d685-111">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="2d685-112">Procedura: Aggiungere e rimuovere elementi da un controllo ComboBox, ListBox o CheckedListBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="2d685-112">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [<span data-ttu-id="2d685-113">Quando usare un controllo ComboBox Windows Form anziché un controllo ListBox</span><span class="sxs-lookup"><span data-stu-id="2d685-113">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)  
 [<span data-ttu-id="2d685-114">Controlli Windows Form usati per elencare opzioni</span><span class="sxs-lookup"><span data-stu-id="2d685-114">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
