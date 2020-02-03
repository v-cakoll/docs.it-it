---
title: Rimuovere elementi da controlli DomainUpDown
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DomainUpDown control [Windows Forms], removing items from
- spin button control [Windows Forms], removing items
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
ms.openlocfilehash: e52af5c5add4fda93e2b51c8afdb90c92e8d2f62
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735773"
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a>Procedura: rimuovere elementi dai controlli DomainUpDown Windows Form
È possibile rimuovere elementi dal controllo Windows Forms <xref:System.Windows.Forms.DomainUpDown> chiamando il metodo <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> o <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> della classe <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>. Il metodo <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> rimuove un elemento specifico, mentre il metodo <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> rimuove un elemento in base alla relativa posizione.  
  
### <a name="to-remove-an-item"></a>Per rimuovere un elemento  
  
- Usare il metodo <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> della classe <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> per rimuovere un elemento in base al nome.  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     -oppure-  
  
- Usare il metodo <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> per rimuovere un elemento in base alla relativa posizione.  
  
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
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>
- [Controllo DomainUpDown](domainupdown-control-windows-forms.md)
- [Panoramica sul controllo DomainUpDown](domainupdown-control-overview-windows-forms.md)
