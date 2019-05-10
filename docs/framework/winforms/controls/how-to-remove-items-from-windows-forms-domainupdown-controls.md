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
ms.openlocfilehash: f56bc2b7b7b8a783ac298b220c83281f38da29da
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662346"
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a>Procedura: Rimuovere elementi dai controlli DomainUpDown di Windows Forms
È possibile rimuovere elementi dall'interno di Windows Form <xref:System.Windows.Forms.DomainUpDown> controllo chiamando la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> o <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> metodo il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> classe. Il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> metodo rimuove un elemento specifico, mentre il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> metodo rimuove un elemento in base alla posizione.  
  
### <a name="to-remove-an-item"></a>Per rimuovere un elemento  
  
- Usare la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> metodo del <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> classe per rimuovere un elemento in base al nome.  
  
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
  
- Usare il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> metodo per rimuovere un elemento in base alla posizione.  
  
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
