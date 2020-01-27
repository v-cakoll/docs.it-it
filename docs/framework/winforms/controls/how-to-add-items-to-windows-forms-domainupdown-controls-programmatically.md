---
title: Aggiungere elementi ai controlli DomainUpDown a livello di codice
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- spin button control [Windows Forms], adding items
- DomainUpDown control [Windows Forms], adding items to
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
ms.openlocfilehash: 2e9f51fa051bf9b62e95f289db97bffd83450036
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745586"
---
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a><span data-ttu-id="5455c-102">Procedura: aggiungere elementi ai controlli DomainUpDown Windows Form a livello di codice</span><span class="sxs-lookup"><span data-stu-id="5455c-102">How to: Add Items to Windows Forms DomainUpDown Controls Programmatically</span></span>
<span data-ttu-id="5455c-103">È possibile aggiungere elementi al controllo Windows Forms <xref:System.Windows.Forms.DomainUpDown> nel codice.</span><span class="sxs-lookup"><span data-stu-id="5455c-103">You can add items to the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control in code.</span></span> <span data-ttu-id="5455c-104">Chiamare il metodo <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> o <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> della classe <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> per aggiungere elementi alla proprietà <xref:System.Windows.Forms.DomainUpDown.Items%2A> del controllo.</span><span class="sxs-lookup"><span data-stu-id="5455c-104">Call the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to add items to the control's <xref:System.Windows.Forms.DomainUpDown.Items%2A> property.</span></span> <span data-ttu-id="5455c-105">Il metodo <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> aggiunge un elemento alla fine di una raccolta, mentre il metodo <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> aggiunge un elemento in una posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="5455c-105">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method adds an item to the end of a collection, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method adds an item at a specified position.</span></span>  
  
### <a name="to-add-a-new-item"></a><span data-ttu-id="5455c-106">Per aggiungere un nuovo elemento</span><span class="sxs-lookup"><span data-stu-id="5455c-106">To add a new item</span></span>  
  
1. <span data-ttu-id="5455c-107">Usare il metodo <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> per aggiungere un elemento alla fine dell'elenco di elementi.</span><span class="sxs-lookup"><span data-stu-id="5455c-107">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method to add an item to the end of the list of items.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     <span data-ttu-id="5455c-108">oppure</span><span class="sxs-lookup"><span data-stu-id="5455c-108">-or-</span></span>  
  
2. <span data-ttu-id="5455c-109">Usare il metodo <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> per inserire un elemento nell'elenco in una posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="5455c-109">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method to insert an item into the list at a specified position.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5455c-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5455c-110">See also</span></span>

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>
- [<span data-ttu-id="5455c-111">Controllo DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="5455c-111">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
- [<span data-ttu-id="5455c-112">Panoramica sul controllo DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="5455c-112">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)
