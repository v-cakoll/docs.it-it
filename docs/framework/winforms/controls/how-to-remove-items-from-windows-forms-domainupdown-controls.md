---
title: 'Procedura: rimuovere elementi dai controlli DomainUpDown Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DomainUpDown control [Windows Forms], removing items from
- spin button control [Windows Forms], removing items
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
ms.openlocfilehash: 702e5e2180148758c4b3775a5cc96a1365703166
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a>Procedura: rimuovere elementi dai controlli DomainUpDown Windows Form
È possibile rimuovere elementi da Windows Form <xref:System.Windows.Forms.DomainUpDown> controllo chiamando la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> o <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> metodo la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> classe. Il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> metodo rimuove un elemento specifico, mentre il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> metodo rimuove un elemento in base alla posizione.  
  
### <a name="to-remove-an-item"></a>Per rimuovere un elemento  
  
-   Utilizzare il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> metodo la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> classe per rimuovere un elemento in base al nome.  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     oppure  
  
-   Utilizzare il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> metodo per rimuovere un elemento in base alla posizione.  
  
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
 <xref:System.Windows.Forms.DomainUpDown>  
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>  
 [Controllo DomainUpDown](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)  
 [Panoramica sul controllo DomainUpDown](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)
