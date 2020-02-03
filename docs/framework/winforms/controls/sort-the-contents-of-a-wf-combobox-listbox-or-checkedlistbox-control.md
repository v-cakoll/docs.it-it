---
title: Ordinare il contenuto di un controllo ComboBox, ListBox o CheckedListBox
ms.date: 03/30/2017
helpviewer_keywords:
- CheckedListBox control [Windows Forms], sorting
- ComboBox control [Windows Forms], sorting contents
- combo boxes [Windows Forms], sorting contents
- list boxes [Windows Forms], sorting contents
- ListBox control [Windows Forms], sorting contents
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
ms.openlocfilehash: dee969d777edf76434622fe632f7e934987a1dc3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742962"
---
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="5b3ac-102">Procedura: ordinare il contenuto di un controllo ComboBox, ListBox o CheckedListBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="5b3ac-102">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="5b3ac-103">I controlli Windows Forms non vengono ordinati quando sono associati a dati.</span><span class="sxs-lookup"><span data-stu-id="5b3ac-103">Windows Forms controls do not sort when they are data-bound.</span></span> <span data-ttu-id="5b3ac-104">Per visualizzare i dati ordinati, utilizzare un'origine dei dati che supporti l'ordinamento e quindi fare in modo che l'origine dati venga ordinata.</span><span class="sxs-lookup"><span data-stu-id="5b3ac-104">To display sorted data, use a data source that supports sorting and then have the data source sort it.</span></span> <span data-ttu-id="5b3ac-105">Le origini dati che supportano l'ordinamento sono viste dati, gestori visualizzazione dati e matrici ordinate.</span><span class="sxs-lookup"><span data-stu-id="5b3ac-105">Data sources that support sorting are data views, data view managers, and sorted arrays.</span></span>  
  
 <span data-ttu-id="5b3ac-106">Se il controllo non è associato a dati, è possibile ordinarlo.</span><span class="sxs-lookup"><span data-stu-id="5b3ac-106">If the control is not data-bound, you can sort it.</span></span>  
  
### <a name="to-sort-the-list"></a><span data-ttu-id="5b3ac-107">Per ordinare l'elenco</span><span class="sxs-lookup"><span data-stu-id="5b3ac-107">To sort the list</span></span>  
  
1. <span data-ttu-id="5b3ac-108">Impostare la proprietà `Sorted` su `true`.</span><span class="sxs-lookup"><span data-stu-id="5b3ac-108">Set the `Sorted` property to `true`.</span></span>  
  
     <span data-ttu-id="5b3ac-109">Questa impostazione riposiziona tutti gli elementi dell'elenco esistenti in base all'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="5b3ac-109">This setting repositions all existing list items in sorted order.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b3ac-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b3ac-110">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [<span data-ttu-id="5b3ac-111">Associazione ai dati di Windows Form</span><span class="sxs-lookup"><span data-stu-id="5b3ac-111">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="5b3ac-112">Procedura: Aggiungere e rimuovere elementi da un controllo ComboBox, ListBox o CheckedListBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="5b3ac-112">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](add-and-remove-items-from-a-wf-combobox.md)
- [<span data-ttu-id="5b3ac-113">Quando usare un controllo ComboBox Windows Form anziché un controllo ListBox</span><span class="sxs-lookup"><span data-stu-id="5b3ac-113">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [<span data-ttu-id="5b3ac-114">Controlli Windows Form usati per elencare opzioni</span><span class="sxs-lookup"><span data-stu-id="5b3ac-114">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
