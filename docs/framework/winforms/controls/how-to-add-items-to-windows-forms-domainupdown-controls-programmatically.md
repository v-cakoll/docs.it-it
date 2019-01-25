---
title: 'Procedura: Aggiungere elementi ai controlli DomainUpDown di Windows Form a livello di codice'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- spin button control [Windows Forms], adding items
- DomainUpDown control [Windows Forms], adding items to
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
ms.openlocfilehash: 865f569da561ec5883b0a0f08fcedb34fc84820c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738560"
---
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a><span data-ttu-id="3e361-102">Procedura: Aggiungere elementi ai controlli DomainUpDown di Windows Form a livello di codice</span><span class="sxs-lookup"><span data-stu-id="3e361-102">How to: Add Items to Windows Forms DomainUpDown Controls Programmatically</span></span>
<span data-ttu-id="3e361-103">È possibile aggiungere elementi ai moduli di Windows <xref:System.Windows.Forms.DomainUpDown> nel codice.</span><span class="sxs-lookup"><span data-stu-id="3e361-103">You can add items to the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control in code.</span></span> <span data-ttu-id="3e361-104">Chiamare il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> o <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> metodo per il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> classe per aggiungere elementi al controllo <xref:System.Windows.Forms.DomainUpDown.Items%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="3e361-104">Call the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to add items to the control's <xref:System.Windows.Forms.DomainUpDown.Items%2A> property.</span></span> <span data-ttu-id="3e361-105">Il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> metodo aggiunge un elemento alla fine di una raccolta, mentre il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> metodo aggiunge un elemento in una posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="3e361-105">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method adds an item to the end of a collection, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method adds an item at a specified position.</span></span>  
  
### <a name="to-add-a-new-item"></a><span data-ttu-id="3e361-106">Per aggiungere un nuovo elemento</span><span class="sxs-lookup"><span data-stu-id="3e361-106">To add a new item</span></span>  
  
1.  <span data-ttu-id="3e361-107">Usare il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> metodo per aggiungere un elemento alla fine dell'elenco di elementi.</span><span class="sxs-lookup"><span data-stu-id="3e361-107">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method to add an item to the end of the list of items.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     <span data-ttu-id="3e361-108">-oppure-</span><span class="sxs-lookup"><span data-stu-id="3e361-108">-or-</span></span>  
  
2.  <span data-ttu-id="3e361-109">Usare il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> metodo per inserire un elemento nell'elenco in una posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="3e361-109">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method to insert an item into the list at a specified position.</span></span>  
  
    ```vb  
    ' Inserts an item at the third position in the list  
    DomainUpDown1.Items.Insert(2, "rice")  
    ```  
  
    ```csharp  
    // Inserts an item at the third position in the list  
    domainUpDown1.Items.Insert(2, "rice");  
    ```  
  
    ```cpp  
    // Inserts an item at the third position in the list  
    domainUpDown1->Items->Insert(2, "rice");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3e361-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e361-110">See also</span></span>
- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>
- [<span data-ttu-id="3e361-111">Controllo DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="3e361-111">DomainUpDown Control</span></span>](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)
- [<span data-ttu-id="3e361-112">Panoramica sul controllo DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="3e361-112">DomainUpDown Control Overview</span></span>](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)
