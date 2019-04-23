---
title: 'Procedura: Rimuovere elementi dai controlli DomainUpDown di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DomainUpDown control [Windows Forms], removing items from
- spin button control [Windows Forms], removing items
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
ms.openlocfilehash: 0c07365f5be2e419b4049a466949fed2d884d897
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59131404"
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a><span data-ttu-id="a4da6-102">Procedura: Rimuovere elementi dai controlli DomainUpDown di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a4da6-102">How to: Remove Items from Windows Forms DomainUpDown Controls</span></span>
<span data-ttu-id="a4da6-103">È possibile rimuovere elementi dall'interno di Windows Form <xref:System.Windows.Forms.DomainUpDown> controllo chiamando la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> o <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> metodo il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> classe.</span><span class="sxs-lookup"><span data-stu-id="a4da6-103">You can remove items from the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control by calling the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class.</span></span> <span data-ttu-id="a4da6-104">Il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> metodo rimuove un elemento specifico, mentre il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> metodo rimuove un elemento in base alla posizione.</span><span class="sxs-lookup"><span data-stu-id="a4da6-104">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method removes a specific item, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method removes an item by its position.</span></span>  
  
### <a name="to-remove-an-item"></a><span data-ttu-id="a4da6-105">Per rimuovere un elemento</span><span class="sxs-lookup"><span data-stu-id="a4da6-105">To remove an item</span></span>  
  
-   <span data-ttu-id="a4da6-106">Usare la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> metodo del <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> classe per rimuovere un elemento in base al nome.</span><span class="sxs-lookup"><span data-stu-id="a4da6-106">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to remove an item by name.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     <span data-ttu-id="a4da6-107">-oppure-</span><span class="sxs-lookup"><span data-stu-id="a4da6-107">-or-</span></span>  
  
-   <span data-ttu-id="a4da6-108">Usare il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> metodo per rimuovere un elemento in base alla posizione.</span><span class="sxs-lookup"><span data-stu-id="a4da6-108">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method to remove an item by its position.</span></span>  
  
    ```vb  
    ' Removes the first item in the list.  
    DomainUpDown1.Items.RemoveAt(0)  
    ```  
  
    ```csharp  
    // Removes the first item in the list.  
    domainUpDown1.Items.RemoveAt(0);  
    ```  
  
    ```cpp  
    // Removes the first item in the list.  
    domainUpDown1->Items->RemoveAt(0);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a4da6-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4da6-109">See also</span></span>

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>
- [<span data-ttu-id="a4da6-110">Controllo DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="a4da6-110">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
- [<span data-ttu-id="a4da6-111">Panoramica sul controllo DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="a4da6-111">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)
